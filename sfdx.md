# sfdx(1)

## Authorize

    sfdx auth:web:login -r https://test.salesforce.com -a \<alias>                     # authorize a sandbox

## Configuration

    sfdx config:list
    sfdx config:set defaultdevhubusername=\<name/alias> -g                             # set default Dev Hub username globally
    sfdx config:set defaultusername=\<name/alias>                                      # set default Scratch Org username

## Create a Scratch Org

    sfdx auth:web:login -a DevHub
    sfdx auth:list
    sfdx force:project:create -x -n myProject
    cd myProject
    cat config/project-scratch-def.json | jq '. += {"language": "en_US"}' > tmp; mv tmp config/project-scratch-def.json
    npm install
    sfdx force:org:create -s -f config/project-scratch-def.json -d 1 -a myScratch1 -v DevHub
    sfdx force:org:list
    sfdx force:org:open -u myScratch1
    ...
    sfdx force:org:delete -u myScratch1

## Start local Development Server for LWC

    sfdx force:lightning:lwc:start
    open http://localhost:3333

## Metadata and Source

    sfdx force:mdapi:describemetadata | jq '.metadataObjects[].xmlName'                     # get all metadata object xml-names
    sfdx force:mdapi:listallmetadata > temp && vd -f json temp                              # inspect all meta data in vd
    sfdx force:mdapi:listmetadata -m ApexClass                                              # list all Apex classes
    sfdx force:mdapi:describemetadata | jq '.metadataObjects[].xmlName'                     # get list of metadata object names

    sfdx force:source:deploy -m LightningComponentBundle:helloWorld                         # deploy a single lightning web component
    sfdx force:source:deploy -x manifest/package.xml --checkonly -u \<alias>                 # verify deployment
    sfdx force:source:retrieve -m ExperienceBundle                                          # retrieve metadata of digital experience pages

## Standard and Custom Objects

    sfdx force:schema:sobject:list -c custom                                                # list all custom objects
    sfdx force:schema:sobject:describe -s \<Obj> | jq '.fields[].name'                       # list all field names of \<object>
    sfdx force:schema:sobject:describe -s \<Obj> | jq -r '.fields[] | "\(.label),\(.name),\(.type)"' | column -t -s,

## SOQL

    sfdx force:data:soql:query -q "SELECT Name FROM Site"
    sfdx force:data:soql:query -q "SELECT \`sfdx force:schema:sobject:describe -s Site | jq -r '.fields[].name' | paste -sd, -` FROM Site" -r csv > logs && vd logs

## Apex Code

    sfdx force:apex:execute                                                                # executes anonymous Apex code in REPL, execute with `CTRL + D`

  Find Object Type from Record ID:

    Id recordId = '8013L000001VkiLQAS';
    System.debug('object is '+ recordId.getsobjecttype());
