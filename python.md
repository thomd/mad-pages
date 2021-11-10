# python(1)

## Best Practices

  create virtual environment

    python -m venv .venv                     # create virtual env in `.venv`
    source venv/bin/activate                 # activate virtual env
    pip install \<package>                    # install packages
    ...
    deactivate

  pretty print a JSON string

    cat data.json | python -m json.tool

  local HTTP server

    python -m http.server 80
    python -m http.server 80 -d test         # serve test folder

  local CGI server

    python -m http.server 80 --cgi           # run scripts in `./cgi-bin/`
    curl localhost/cgi-bin/test.py
