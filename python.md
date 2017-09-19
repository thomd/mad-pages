# python(1)

## Best Practices

  pretty print a JSON string

    cat data.json | python -m json.tool

  local HTTP server

    python -m SimpleHTTPServer 8000                   # python 2
    python -m http.server 8000                        # python 3
