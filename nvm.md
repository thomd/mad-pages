
# nvm(1)

use versions

    nvm ls                                  # list installed nodes
    nvm ls-remote                           # list installable nodes
    nvm use \<version>                       # use a specific version
    nvm use default                         # use defined default version
    nvm alias default \<version>             # set \<version> as the default node

install new version

    nvm install \<version>                   # install <version>
    nvm install --lts                       # install latest LTS version
    nvm install \<lts_name>                  # install specific LTS version
    nvm reinstall-packages \<version>        # reinstall global npm packages contained in <version> to current version

cleanup

    nvm cache dir                           # display path to the cache directory for nvm
    nvm cache clear                         # empty cache directory for nvm
    nvm uninstall \<version>                 # uninstall a version

