
# ssh(1)

## ssh-keygen(1)

generate a keypair

    cd ~/.ssh
    ssh-keygen -t rsa

    ssh-keygen -t rsa -C my@email.com -f ~/.ssh/github

show fingerprint of a public key

    ssh-keygen -l -f ~/.ssh/github.pub

