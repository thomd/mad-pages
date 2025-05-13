# jwt-cli(1)

## Encode JWT

    jwt encode --secret 123 --payload name=foo                    # generate JWT with claims name and iat and sign with secret 123
    jwt encode --secret 123 --exp=10s --payload name=foo          # generate JWT with claims name, iat and exp (10 sec) and sign with secret 123

## Decode JWT

    jwt decode TOKEN
    echo TOKEN | jwt decode -
    jwt decode --secret 123 TOKEN                                 # validate JWT with secret 123
