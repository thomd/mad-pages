
# apt-get(1)

    apt-get update
    apt-get install -y \<package>
    
    apt-get autoclean
    apt-get download \<package>              # download and then use dpkg(1)

# apt-cache(1)

    apt-cache pkgnames \<package>            # list all the packages starting with \<package>
    apt-cache search \<package>              # list specific packages with short description
    apt-cache show \<package>                # show package information

# aptitude(8)

aptitude is a terminal-based frontend for apt.

    aptitude                                # start aptitude GUI

# dpkg(1)

dpkg just installs a `.deb` file, but not its dependencies.


    dpkg -I \<package.deb>                   # show package information
    dpkg -c \<package.deb>                   # show contends of package.deb
    dpkg -i \<package.deb>                   # install a package (no dependencies installed!)
    dpkg -r \<package>                       # remove a package
