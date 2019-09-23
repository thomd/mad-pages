
# python(1)

## Virtualenvwrapper

Packages are stored in `~/.virtualenvs/`

    mkvirtualenv -p python3 my\_project          # create and activate a new project
    workon my\_project                           # switch into virtualenv of my\_project
    deactivate

    lsvirtualenv                                # list virtualenv projects
    rmvirtualenv my\_project                     # delete virtualenv project
    lssitepackages                              # list site-packages
    cdvirtualenv                                # cd into currently activated virtual environment

## Best Practices

  pretty print a JSON string

    cat data.json | python -m json.tool

  local HTTP server

    python -m SimpleHTTPServer 8000                   # python 2
    python -m http.server 8000                        # python 3
