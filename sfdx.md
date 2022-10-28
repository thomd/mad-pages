# sfdx(1)

## Configuration

    sfdx config:list
    sfdx config:set defaultdevhubusername=\<name/alias> -g                             # set default Dev Hub username globally
    sfdx config:set defaultusername=\<name/alias>                                      # set default Scratch Org username

## Create a Scratch Org

    sfdx auth:web:login -a myDevHub
    sfdx auth:list
    sfdx force:project:create -x -n myProject
    cd myProject
    cat config/project-scratch-def.json | jq '. += {"language": "en_US"}' > tmp; mv tmp config/project-scratch-def.json
    sfdx force:org:create -s -f config/project-scratch-def.json -d 1 -a myScratch -v myDevHub
    sfdx force:org:list
    sfdx force:org:open -u myScratch
    ...
    sfdx force:org:delete -u myScratch

## Start local Development Server for LWC

    sfdx force:lightning:lwc:start
    open http://localhost:3333

## Source and Metadata

    sfdx force:source:deploy -m LightningComponentBundle:helloWorld                    # deploy a single lightning web component
    sfdx force:source:retrieve -m ExperienceBundle                                     # retrieve metadata of digital experience pages

## Standard and Custom Objects

    sfdx force:schema:sobject:list -c custom                                           # list all custom objects
    sfdx force:schema:sobject:describe -s \<Object> | jq '.fields[].name'               # list all field names of \<object>

## SOQL

    sfdx force:data:soql:query -q "SELECT Name FROM Site"
    sfdx force:data:soql:query -q "SELECT \`sfdx force:schema:sobject:describe -s Site | jq -r '.fields[].name' | paste -sd, -` FROM Site"
