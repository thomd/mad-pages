# sf(1)

## Update

    npm install -g @salesforce/cli; sf plugins reset; sf info releasenotes display

## Authorize

    sf org login web -r https://test.salesforce.com -a \<org>                                      # authorize sandbox
    sf org login web -r https://DomainName--\<org>.sandbox.my.salesforce.com -a \<org>             # authorize sandbox
    sf org login web -r https://login.salesforce.com -a \<org>                                     # authorize playground or production-org
    sf org logout -o \<org>

## Configuration

    sf config list
    sf config set target-org \<org>                                  # set default org
    sf config set -g target-org \<org>                               # set default org globally
    sf config set target-dev-hub \<org>                              # set default DevHub org

## Create Minimal SFDX Project

    echo '{"packageDirectories": [{"path": "force-app"}]}' > sfdx-project.json; mkdir force-app
    sf config set target-org \<org>
    code .

## Debug Log

    sf apex list log
    sf apex tail log -c -s | spacer
    script -q /dev/null sf apex tail log -c -s | tee debug.log

## Query Data

    sf sobject list
    sf sobject describe -s \<object>
    sf data query -q "select \<fields> from \<object>" -r csv

## Execute Anonymous Apex Code

    nodemon -e "sf apex run -f" my.apex
    vim my.apex

## Execute Apex Test

    sf apex run test -yc -n MyClassTest
    sf apex run test -yc -l \<test-level>                         # with test-level = RunSpecifiedTests | RunLocalTests | RunAllTestsInOrg

## Determine Object Type

    sf data query -t -q "SELECT Label, QualifiedApiName FROM EntityDefinition WHERE KeyPrefix='001'"
