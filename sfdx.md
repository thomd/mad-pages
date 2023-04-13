# sfdx(1)

## Authorize

    sfdx auth web login -r https://test.salesforce.com -a \<alias>      # authorize sandbox
    sfdx auth web login -r https://login.salesforce.com -a \<alias>     # authorize playground or production-org

## Configuration

    sfdx config list
    sfdx config set defaultusername=\<alias>                            # set default Scratch Org username

## Create a Scratch Org

    sfdx project generate -x -n myProject
    cat config/project-scratch-def.json | jq '. += {"language": "en_US"}' > tmp; mv tmp config/project-scratch-def.json
    sfdx org create scratch -f config/project-scratch-def.json -v DevHub -a scratch1
    sfdx org open -o scratch1
    ...
    sfdx org delete -o scratch1

## Source

  Package based Deployment

    sfdx force source deploy -x manifest/package.xml --checkonly -u \<alias>
    nodemon --watch force-app --ext "cls,xml,js,html" --exec "sfdx force source deploy -m LightningComponentBundle:\*,ApexClass:\*"

  Quickstart DX Project:

    echo '{"packageDirectories": [{"path": "force-app"}]}' > sfdx-project.json
    mkdir force-app
    sfdx config set defaultusername=\<alias>
    sfdx org open
    code .
    sfdx force source deploy -p force-app

## Metadata

  Get Metadata Type Names

    sfdx force mdapi describemetadata | jq -r '.metadataObjects[].xmlName'
    sfdx force mdapi describemetadata | jq -r '.metadataObjects[] | if (.childXmlNames | length) == 0 then .xmlName else .childXmlNames[] end'

  Get Metadata Type Members

    sfdx force mdapi listmetadata -m \<name> | jq -r '.[].fullName'

  Retrieve Metadata of one Type Member

    sfdx force source retrieve -m \<name>:\<member>

  Retrieve all Metadata:

    while read -r t; do sfdx force source retrieve -m $t; done < <(sfdx force mdapi describemetadata | jq -r '.metadataObjects[].xmlName')
    while read -r t; do sfdx force source retrieve -m $t; done < <(sfdx force mdapi describemetadata | jq -r '.metadataObjects[] | if (.childXmlNames | length) == 0 then .xmlName else .childXmlNames[] end')

  Generate incremental deployments manifests

    sfdx sgd source delta -f develop -o .
    sfdx force source deploy -x package/package.xml --postdestructivechanges destructiveChanges/destructiveChanges.xml

## Standard and Custom Objects

    sfdx force schema sobject list -c custom                                                # list all custom objects
    sfdx force schema sobject describe -s \<Obj> | jq '.fields[].name'                       # list all field names of \<object>
    sfdx force schema sobject describe -s \<Obj> | jq -r '.fields[] | "\(.label),\(.name),\(.type)"' | column -t -s,

## Query

    sfdx data query -q "SELECT Name FROM Site"

  Retrieve all data of an object:

    sfdx data query -q "SELECT \`sfdx force schema sobject describe -s User | jq -r '.fields[].name' | paste -sd, -` FROM User" -r csv

  Check CRUD permissions:

    sfdx data query -q "SELECT RecordId, MaxAccessLevel, HasAllAccess, HasDeleteAccess, HasEditAccess, HasReadAccess, HasTransferAccess FROM UserRecordAccess WHERE UserId = '\<id>' AND RecordId = '\<id>'

## Apex Code

    sfdx force apex execute                                                                # executes anonymous Apex code in REPL, execute with `CTRL + D`
    sfdx force apex test run -l RunAllTestsInOrg -c -r human -y                            # run all test in org and display code coverage
    sfdx force apex test run -t MyTestClass -y                                             # run a specific test class

## B2B Theme

    (cd frontend && npm run frontend:build)
    sfdx force:source:deploy -m StaticResource:b2bTheme
    sfdx force:source:deploy -m AuraDefinitionBundle:b2bTheme

## Experience Builder

    sfdx force community publish -n \<site> -o \<org>                                        # publish site

