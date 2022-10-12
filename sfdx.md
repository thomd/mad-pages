# sfdx

## Create a Scratch Org

    sfdx auth:web:login -a myDevHub
    sfdx auth:list
    sfdx force:project:create -n myProject
    cd myProject
    cat config/project-scratch-def.json | jq '. += {"language": "en_US"}' > tmp; mv tmp config/project-scratch-def.json
    sfdx force:org:create -s -f config/project-scratch-def.json -d 1 -a myScratch
    sfdx force:org:list
    sfdx force:org:open -u myScratch
    sfdx force:org:delete -u myScratch

## Configuration

    sfdx config:list
    sfdx config:set defaultdevhubusername=\<name/alias> -g                 # set default Dev Hub username globally
    sfdx config:set defaultusername=\<name/alias>                          # set default Scratch Org username

## Start local Development Server for LWC

    sfdx force:lightning:lwc:start
    open http://localhost:3333
