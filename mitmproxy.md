# mitmproxy(1)

    mitmproxy --anticache                                       # strip out request headers that might cause the server to return 304-not-modified
    mitmproxy --anticomp                                        # try to convince servers to send us un-compressed data
    mitmproxy --no-http2                                        # disable HTTP/2 support. HTTP/2 support is enabled by default
    mitmproxy --ssl-insecure                                    # skips mitmproxy's certificate verification
    mitmproxy -p 8888                                           # run with custom port (default: 8080)
    mitmproxy -s script.py                                      # execute a script

    mitmproxy --anticache --replacements "/~s/foo/bar"         # replace 'foo' with 'bar'

## Scripts

Set Custom Header

        # custom-header.py
        from mitmproxy import http
        def request(flow):
            flow.request.headers["myheader"] = "value"

    mitmproxy -s custom-header.py

