# gpg(1)

    gpg -K                              # list secret keys
    gpg -k                              # list public keys
    gpg -a --export \<id>                # export public key in ASCII format to stdout

Symmetric (AES-128)

    gpg -c file.txt                     # encrypt with a symmetric cipher (use '--no-symkey-cache' to disable passphrase caching)
    gpg -d file.txt.gpg                 # decrypt the file with the same passphrase (using gpg-agent)

Asymmetric (with Public Key)

    gpg -e -r \<id> file.txt             # encrypt for recipient \<id> with recipients public key
    gpg -d file.txt.gpg                 # decrypt file using recipients private key
