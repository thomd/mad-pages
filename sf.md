# sf(1)

## Authorize

    sf org login web -r https://test.salesforce.com -a \<org>        # authorize sandbox
    sf org login web -r https://login.salesforce.com -a \<org>       # authorize playground or production-org
    sf org logout -o \<org>

## Configuration

    sf config list
    sf config set target-org \<org>                                  # set default org
    sf config set -g target-org \<org>                               # set default org globally
    sf config set target-dev-hub \<org>                              # set default DevHub org

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

    sf apex list log
    sf apex tail log -c -s
    script -q /dev/null sf apex tail log -c -s | tee debug.log

## Query Data

    sf data query -q "\<soql>" -r csv

## Execute Apex Test

    sf apex run test -yc -n MyClassTest
    sf apex run test -yc -l \<test-level>                         # with test-level = RunSpecifiedTests | RunLocalTests | RunAllTestsInOrg

## Determine Object Type

    sf data query -t -q "SELECT Label, QualifiedApiName FROM EntityDefinition WHERE KeyPrefix='005'"
