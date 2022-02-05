# pyenv(1)

  Install new Python Version

    pyenv version                     # list current version
    pyenv versions                    # list installed versions
    pyenv install --list              # list all available versions
    pyenv install VERSION             # install version VERSION
    pyenv uninstall VERSION           # uninstall version VERSION

  Use a Python Version

    pyenv global VERSION              # set default global version
    pyenv local VERSION               # set version to be used in a particular directory (see .python-version file)
    pyenv shell VERSION               # set version to be used in the current shell
    pyenv shell system                # set system-version to be used in the current shell

pyenv's version lookup path is:

* the `PYENV_VERSION` variable (which you can set with pyenv shell)
the directory's .python_version file (which we can change with pyenv shell for a one-time change, or pyenv local for something more permanent)
the first .python_version file it can find, recursively searching each parent directory until it reaches root
the global $(pyenv root)/version file, which you can modify with pyenv global

