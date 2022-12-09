# gpg(1)

    gpg -K                              # list secret keys
    gpg -k                              # list public keys
    gpg -a --export <id>                # export public key in ASCII format to stdout

Symmetric (via passphrase)

    gpg -c file.txt                     # encrypt using a passphrase (with a symmetric cipher)
    gpg file.txt.gpg                    # decrypt the file using the same passphrase

Asymmetric (via public key)


