
# nvm(1)

Use Version

    nvm ls                                  # list installed nodes
    nvm ls-remote                           # list installable nodes
    nvm use VERSION                         # use a specific version
    nvm use default                         # use defined default version
    nvm alias default VERSION               # set default

Install Version

    nvm install VERSION                     # install <version>
    nvm install-latest-npm                  # install latest npm
    nvm install --lts                       # install latest LTS version
    nvm reinstall-packages VERSION          # reinstall global npm packages contained in <version> to current version

Cleanup

    nvm cache dir                           # display path to the cache directory for nvm
    nvm cache clear                         # empty cache directory for nvm
    nvm uninstall VERSION                   # uninstall a version

