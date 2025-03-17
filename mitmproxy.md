# mitmproxy(1)

    mitmproxy --anticache                                       # strip out request headers that might cause the server to return 304-not-modified
    mitmproxy --anticomp                                        # try to convince servers to send us un-compressed data
    mitmproxy --no-http2                                        # disable HTTP/2 support. HTTP/2 support is enabled by default
    mitmproxy --ssl-insecure                                    # skips mitmproxy's certificate verification
    mitmproxy -p 8888                                           # run with custom port (default: 8080)
    mitmproxy -s script.py                                      # execute a script

    mitmproxy --anticache --replacements "/~s/foo/bar"          # replace 'foo' with 'bar'

## Scripts

  Set Custom Header

        # custom-header.py
         from mitmproxy import http
         def request(flow):
             flow.request.headers["myheader"] = "value"

    mitmproxy -s custom-header.py

## Intercept Requests

  Intercept Requests with Node.js

    export HTTP\_PROXY="http://localhost:8080"
    export HTTPS\_PROXY="http://localhost:8080"
    export NODE\_TLS\_REJECT\_UNAUTHORIZED=0
    export NODE\_NO\_WARNINGS=1

  Intercept Requests with Python

    export HTTP\_PROXY="http://localhost:8080"
    export HTTPS\_PROXY="https://localhost:8080"
    export REQUESTS\_CA\_BUNDLE="/Users/tduerr/.mitmproxy/mitmproxy-ca.pem"
