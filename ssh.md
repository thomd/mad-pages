
# ssh(1)

login

    ssh -i ~/.ssh/key_name user@host

# ssh-keygen(1)

generate a keypair

    ssh-keygen -t rsa -f ~/.ssh/name

show fingerprint of a public key

    ssh-keygen -l -f ~/.ssh/name.pub

# Socks Proxy via SSH Tunnel

    ssh -fN -D localhost:3128 user@host

If using the `-fN` option, connection needs to be killed manually with `ps ax | grep ssh`

Test socks proxy with

    curl ifconfig.co
    curl --socks5 localhost:3128 ifconfig.co

