# sfdx

## Create a Scratch Org

    sfdx auth:web:login -d -a DevHub
    sfdx auth:list
    sfdx force:project:create -n myProject
    cd myProject
    cat config/project-scratch-def.json | jq '. += {"language": "en_US"}' > tmp; mv tmp config/project-scratch-def.json
    sfdx force:org:create -s -f config/project-scratch-def.json -d 1 -a MyScratch
    sfdx force:org:list
    sfdx force:org:open -u MyScratch
    sfdx force:org:delete -u MyScratch
