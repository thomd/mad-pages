# Development Tools

## Serve Localhost

    npx serve -l 8080                 # local HTTP webserver using Nodejs
    python -m http.server 8080        # local HTTP webserver using Python

## Reverse Proxy to Localhost

    ngrok http 8080                                # open http tunnel for port 8080 (expose HTTP or TLS)
    ngrok http -host-header=example.com 80         # rewrite the Host header
    ngrok http -auth="username:password" 8080      # password-protect your tunnel
    ngrok http -region=eu 8080                     # use EU tunnel
    ngrok tcp 22                                   # Expose a SSH server / SFTP server listening on the default port
