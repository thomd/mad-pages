
# verify if certificate fits to private key

  extract public key from private key:

    openssl pkey -in \<PRIVATEKEY> -pubout

  extract public key from certificate:

    openssl x509 -in \<CERTIFICATE> -noout -pubkey

  if both are the same, then certificate fits to private key

# verify certificate

    openssl verify -CAfile \<(cat \<INTERMEDIATE-CA> \<CA-CERT>) \<CERT-TO-CHECK>

