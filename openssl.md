# openssl(1)

## Verify if Certificate fits to Private Key

  extract public key from private key:

    openssl pkey -in PRIVATEKEY -pubout

  extract public key from certificate:

    openssl x509 -in CERTIFICATE -noout -pubkey

  if both are the same, then certificate fits to private key

## Verify Certificate

    openssl verify -CAfile \<(cat INTERMEDIATE-CA CA-CERT) CERT-TO-CHECK

