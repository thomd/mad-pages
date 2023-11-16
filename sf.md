# sf(1)

## Authorize

    sf org login web -r https://test.salesforce.com -a \<alias>        # authorize sandbox
    sf org login web -r https://login.salesforce.com -a \<alias>       # authorize playground or production-org
    sf org logout -o \<alias>

## Configuration

    sf config list
    sf config set target-org \<alias>                                  # set default target org
    sf config set target-dev-hub  \<alias>                             # set default Dev Hub org

## Validation

    sf project deploy validate -x manifest/package.xml -o \<org>
    sf project deploy validate -x manifest/package.xml -l RunSpecifiedTests \`sed s/,$// scripts/test/unit-test-list.txt | awk '{ printf(" -t %s", $0) }'\` -o \<org>

## Deploy to Org

    sf project deploy start -x manifest/package.xml --concise -o \<org>
    sf project deploy start -m LightningComponentBundle:\* -m ApexClass:\* -o \<org>
    nodemon -w force-app -e "cls,xml,js,html" -x "sf project deploy start -m LightningComponentBundle:\* -m ApexClass:\*"

## Retrieve from Org

    sf project retrieve start -x manifest/package.xml -o \<org>
    sf project retrieve start -m ApexClass:MyApexClass -o \<org>

## Debug Log

    sf apex tail log -c -s
    script -q /dev/null sf apex tail log -c -s | tee debug.log

## Query Data

    sd data query -q "<soql>" -r csv

