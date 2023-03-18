# sfdx(1)

## Authorize

    sfdx auth web login -r https://test.salesforce.com -a \<alias>                     # authorize sandbox
    sfdx auth web login -r https://login.salesforce.com -a \<alias>                    # authorize playground or production-org

## Configuration

    sfdx config list
    sfdx config set defaultusername=\<alias>                                           # set default Scratch Org username

## Create a Scratch Org

    sfdx project generate -x -n myProject
    cat config/project-scratch-def.json | jq '. += {"language": "en_US"}' > tmp; mv tmp config/project-scratch-def.json
    sfdx org create scratch -f config/project-scratch-def.json -a scratch1 -v DevHub
    sfdx org open -o scratch1
    ...
    sfdx org delete -o scratch1

## Source

  Package based Deployment

    sfdx force source deploy -x manifest/package.xml --checkonly -u \<alias>
    nodemon --watch force-app --ext "cls,xml,js,html" --exec "sfdx force source deploy -m LightningComponentBundle:\*,ApexClass:\*"

  Quickstart DX Project:

    echo '{"packageDirectories": [{"path": "force-app"}]}' > sfdx-project.json
    sfdx config set defaultusername=\<alias>
    code .
    sfdx force source deploy -p force-app

## Metadata

  Metadata Types

    sfdx force mdapi describemetadata | jq -r '.metadataObjects[].xmlName'                  # get all metadata type names

        ApexClass
        CustomObject
        CustomField
        CustomLabel
        ExperienceBundle
        Flow
        LightningComponentBundle

    sfdx force mdapi listmetadata -m \<name> | jq -r '.[].fullName'                          # get all metadata type-members
    sfdx force source retrieve -m \<name>:\<member>                                           # retrieve metadata

## Standard and Custom Objects

    sfdx force schema sobject list -c custom                                                # list all custom objects
    sfdx force schema sobject describe -s \<Obj> | jq '.fields[].name'                       # list all field names of \<object>
    sfdx force schema sobject describe -s \<Obj> | jq -r '.fields[] | "\(.label),\(.name),\(.type)"' | column -t -s,

## Query

    sfdx data query -q "SELECT Name FROM Site"
    sfdx data query -q "SELECT \`sfdx force schema sobject describe -s User | jq -r '.fields[].name' | paste -sd, -` FROM User" -r csv > user.csv && vd user.csv

## Apex Code

    sfdx force apex execute                                                                # executes anonymous Apex code in REPL, execute with `CTRL + D`

  Find Object Type from Record ID:

    Id recordId = '8013L000001VkiLQAS';
    System.debug('object is '+ recordId.getsobjecttype());

## B2B Theme

    (cd frontend && npm run frontend:build)
    sfdx force:source:deploy -m StaticResource:b2bTheme
    sfdx force:source:deploy -m AuraDefinitionBundle:b2bTheme

## Experience Builder

    sfdx force community publish -n \<site> -o \<org>                                        # publish site
