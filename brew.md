# brew(1)

## Info

    brew search <package>
    brew info <package>               # show package short info 
    brew list                         # list installed packages
    brew list --cask                  # list installed casks (macOS native applications)
    brew list <package>               # list all files of an installed package

## Install

    brew install <package>            # install a package
    brew install <url>                # install a package from url
    brew install <path-to-formula>    # install a package from path 
    brew uninstall <package>          # uninstall a package

## Upgrade

    brew outdated                     # show which installed packages are out of date
    brew upgrade <package>

## Cleanup

    brew cleanup                      # remove outdated versions from the cellar
    brew cleanup -n                   # dry-run
    brew cleanup <package>            # remove outdated versions of a package

## Services

If sudo is passed, operate on /Library/LaunchDaemons (started at boot). Otherwise, operate on ~/Library/LaunchAgents (started at login).

    brew services list                # services for the current user (or root)
    brew services run <formula>       # run service <formula> without registering to launch at login
    brew services start <formula>     # start service <formula> and register it to launch at login
    brew services stop <formula>      # stop service <formula> and unregister it from launching at login
    brew services cleanup             # remove all unused services
