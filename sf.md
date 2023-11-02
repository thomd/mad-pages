# sf(1)

## Authorize

    sf org login web -r https://test.salesforce.com -a \<alias>        # authorize sandbox
    sf org login web -r https://login.salesforce.com -a \<alias>       # authorize playground or production-org
    sf org logout -o \<alias>

## Configuration

    sf config list
    sf config set target-org \<alias>                                  # set default username

## Validation

    sf project deploy validate -x manifest/package.xml -o \<org>
    sf project deploy validate -x manifest/package.xml -l RunSpecifiedTests `sed s/,$// scripts/test/unit-test-list.txt | awk '{ printf(" -t %s", $0) }'` -o \<org>

## Deploy to Org

    sf project deploy start -x manifest/package.xml --concise -o \<org>
    sf project deploy start -m LightningComponentBundle:\* -m ApexClass:\* -o \<org>
    nodemon --watch force-app --ext "cls,xml,js,html" --exec "sf project deploy start -m LightningComponentBundle:\* -m ApexClass:\*"

## Retrieve from Org

    sf project retrieve start -x manifest/package.xml -o \<org>
    sf project retrieve start -m ApexClass:MyApexClass -o \<org>

## Quickstart Salesforce DX Project

    echo '{"packageDirectories": [{"path": "force-app"}]}' > sfdx-project.json
    mkdir force-app
    sf config set target-org \<alias>
    sf org open
    code .
    sf project deploy start -p force-app

## Debug Log

    sf apex tail log -c -s
    script -q /dev/null sf apex tail log -c -s | tee debug.log

## Metadata

  Get Metadata Type Names

    sfdx org list metadata-types | jq -r '.metadataObjects[].xmlName'
    sfdx org list metadata-types | jq -r '.metadataObjects[] | if (.childXmlNames | length) == 0 then .xmlName else .childXmlNames[] end'

  Get Metadata Type Members

    sfdx force mdapi listmetadata -m \<name> | jq -r '.[].fullName'

  Retrieve Metadata of one Type Member

    sfdx project retrieve start -m \<name>:\<member>

  Generate Incremental Deployments Manifests

    sfdx sgd source delta -f develop -o .
    sfdx sgd source delta -f HEAD~1 -t HEAD -o .
    sfdx force source deploy -x package/package.xml --postdestructivechanges destructiveChanges/destructiveChanges.xml

## Data

  Get Fields of an Object

    sfdx sobject list -s custom                                                                           # list all custom objects [all|custom|standard]
    sfdx sobject describe -s \<obj> | jq '.fields[].name' | paste -sd, -                                   # list all field names of \<obj> comma-separated
    sfdx sobject describe -s \<obj> | jq -r '.fields[] | "\(.label),\(.name),\(.type)"' | column -t -s,    # list all field names, labels and type of \<obj> in a table

  Get Records of an Object

    sfdx data query -q "SELECT \`sfdx force schema sobject describe -s User | jq -r '.fields[].name' | paste -sd, -` FROM User" -r csv

  SOQL Queries

    sfdx data query -q "SELECT Name FROM Site" -r csv

## Apex Unit Test

    sfdx apex run test -l RunAllTestsInOrg -c -r human -y                            # run all test in org and display code coverage
    sfdx apex run test -n MyClassTest -c -r human -y                                 # run a specific test class
