# virtualenv

## Virtualenvwrapper

Packages are stored in `~/.virtualenvs/`

    mkvirtualenv my\_project                     # create and activate a new project
    workon my\_project                           # switch into virtualenv of my\_project
    deactivate

    lsvirtualenv -b                             # list virtualenv projects
    rmvirtualenv my\_project                     # delete virtualenv project
    lssitepackages                              # list site-packages
    cdvirtualenv                                # cd into currently activated virtual environment

    pip install PKG
    pip install -r requirements.txt             # install dependencies
