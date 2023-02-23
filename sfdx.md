# sfdx(1)

## Authorize

    sfdx auth web login -r https://test.salesforce.com -a \<alias>                     # authorize sandbox
    sfdx auth web login -r https://login.salesforce.com -a \<alias>                    # authorize playground or production-org

## Configuration

    sfdx config list
    sfdx config set defaultusername=\<alias>                                           # set default Scratch Org username

## Create a Scratch Org

    sfdx force project create -x -n myProject
    cat config/project-scratch-def.json | jq '. += {"language": "en_US"}' > tmp; mv tmp config/project-scratch-def.json
    npm install
    sfdx force org create -s -f config/project-scratch-def.json -d 30 -a myScratch1 -v DevHub
    sfdx force org list
    sfdx force org open -o myScratch1
    ...
    sfdx force org delete -o myScratch1

## Metadata and Source

    sfdx force mdapi listallmetadata > temp && vd -f json temp                              # inspect all meta data in vd
    sfdx force mdapi listmetadata -m ApexClass                                              # list all Apex classes
    sfdx force mdapi describemetadata | jq '.metadataObjects[].xmlName'                     # get list of metadata object names

    sfdx force source retrieve -m \<type>:\<member>                                           # retrieve metadata
    sfdx force source deploy -x manifest/package.xml --checkonly -u \<alias>                 # verify deployment

  Metadata Types

    sfdx force mdapi describemetadata | jq -r '.metadataObjects[].xmlName'                  # get all metadata types

        ApexClass
        CustomObject
        CustomField
        CustomLabel
        ExperienceBundle
        Flow
        LightningComponentBundle

  Minimal DX Project `sfdx-project.json`

    {"packageDirectories": [{"path": "."}]}

## Standard and Custom Objects

    sfdx force schema sobject list -c custom                                                # list all custom objects
    sfdx force schema sobject describe -s \<Obj> | jq '.fields[].name'                       # list all field names of \<object>
    sfdx force schema sobject describe -s \<Obj> | jq -r '.fields[] | "\(.label),\(.name),\(.type)"' | column -t -s,

## Query

    sfdx data query -q "SELECT Name FROM Site"
    sfdx data query -q "SELECT \`sfdx force schema sobject describe -s Site | jq -r '.fields[].name' | paste -sd, -` FROM Site" -r csv > logs && vd logs

## Apex Code

    sfdx force apex execute                                                                # executes anonymous Apex code in REPL, execute with `CTRL + D`

  Find Object Type from Record ID:

    Id recordId = '8013L000001VkiLQAS';
    System.debug('object is '+ recordId.getsobjecttype());

## B2B Theme

    (cd frontend && npm run frontend:build)
    sfdx force:source:deploy -m StaticResource:b2bTheme
    sfdx force:source:deploy -m AuraDefinitionBundle:b2bTheme
