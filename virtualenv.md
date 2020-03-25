# virtualenv

## Virtualenvwrapper

Packages are stored in `~/.virtualenvs/`

    mkvirtualenv -p python3 my\_project          # create and activate a new project
    workon my\_project                           # switch into virtualenv of my\_project
    deactivate

    lsvirtualenv                                # list virtualenv projects
    rmvirtualenv my\_project                     # delete virtualenv project
    lssitepackages                              # list site-packages
    cdvirtualenv                                # cd into currently activated virtual environment


