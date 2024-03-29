# sfdx(1)

## Authorize

    sfdx auth web login -r https://test.salesforce.com -a \<alias>      # authorize sandbox
    sfdx auth web login -r https://login.salesforce.com -a \<alias>     # authorize playground or production-org
    sfdx auth logout -o \<alias>

## Configuration

    sfdx config list
    sfdx config set target-org=\<alias>                            # set default Scratch Org username
    sfdx config set -g target-org=\<alias>                         # set default Scratch Org username globally

## Create a Scratch Org

    sfdx project generate -x -n myProject && cd myProject
    cat config/project-scratch-def.json | jq '. += {"language": "en_US"}' > tmp; mv tmp config/project-scratch-def.json
    sfdx org create scratch -f config/project-scratch-def.json -y 30 -v DevHub -a scratch1
    sfdx org open -o scratch1
    ...
    sfdx org delete scratch -o scratch1

## Source

  Package based Deployment

    sfdx force source deploy -x manifest/package.xml --checkonly -u \<alias>
    nodemon --watch force-app --ext "cls,xml,js,html" --exec "sfdx force source deploy -m LightningComponentBundle:\*,ApexClass:\*"

  Deploy Validate

    sfdx force source deploy -x manifest/package.xml -u b2bdevqa -l RunSpecifiedTests -r \`cat scripts/test/unit-test-list.txt | awk '{ printf("%s", $0) }'\` -c --verbose

  Quickstart Salesforce DX Project:

    echo '{"packageDirectories": [{"path": "force-app"}]}' > sfdx-project.json
    mkdir force-app
    sfdx config set defaultusername=\<alias>
    sfdx org open
    code .
    sfdx force source deploy -p force-app

## Debug Log

    sfdx apex log tail -c -s -o \<org>
    script -q /dev/null sfdx apex log tail -c -s -o \<org> | tee debug.log

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

## B2B Theme

    (cd frontend && npm run frontend:build)
    sfdx force source deploy -m StaticResource:b2bTheme
    sfdx force source deploy -m AuraDefinitionBundle:b2bTheme

    nodemon -w frontend -e "scss" -x "(cd frontend && npm run frontend:build:deploy)"

## Experience Builder

    sfdx community publish -n \<site> -o \<org>                                        # publish site

