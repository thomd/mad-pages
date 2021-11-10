# venv

venv is the recommended method for creating virtual environments

    python -m venv -h

  Usage

    python -m venv venv                      # create virtual env `"venv"`
    source venv/bin/activate                 # activate virtual env
    pip install \<package>                    # install packages
    ...
    deactivate

# python(1)

## Best Practices

  pretty print a JSON string

    cat data.json | python -m json.tool

  local HTTP server

    python -m http.server 80
    python -m http.server 80 -d test         # serve test folder
