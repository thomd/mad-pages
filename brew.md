# brew(1)

## Info

    brew search \<package>
    brew info \<package>               # show package short info 
    brew list                         # list installed packages
    brew list --cask                  # list installed casks (macOS native applications)
    brew list \<package>               # list all files of an installed package

## Install

    brew install \<package>            # install a package
    brew uninstall \<package>          # uninstall a package

## Upgrade

    brew outdated                     # show which installed packages are out of date
    brew upgrade \<package>

## Cleanup

    brew cleanup                      # remove outdated versions from the cellar
    brew cleanup -n                   # dry-run
    brew cleanup \<package>            # remove outdated versions of a package

## Services

If sudo is passed, operate on /Library/LaunchDaemons (started at boot). Otherwise, operate on ~/Library/LaunchAgents (started at login).

    brew services list                # services for the current user (or root)
    brew services run \<package>       # run service \<package> without registering to launch at login
    brew services start \<package>     # start service \<package> and register it to launch at login
    brew services stop \<package>      # stop service \<package> and unregister it from launching at login
    brew services cleanup             # remove all unused services
