# ngrok(1)

ngrok is an open reverse proxy to localhost.

    ngrok 8000
    ngrok http 8080                                # open http tunnel for port 8080 (expose HTTP or TLS)
    ngrok http -host-header=example.com 80         # rewrite the Host header
    ngrok tcp 22                                   # Expose a SSH server listening on the default port
    ngrok tcp 5432                                 # Expose a Postgres server listening on the default port

## Inspect traffic

    open http://localhost:4040

## Get Public Address

    curl -s http://localhost:4040/api/tunnels | jq -r '.tunnels[1].public_url'
