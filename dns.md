# DNS

## hosts file

    sudo vim /ets/hosts                    # assign hostname to IP
    sudo dscacheutil -flushcache           # flush dns cache

## dig(1)

  Syntax

    dig \<options> @\<nameserver> \<name> \<type>

  with type: `A` (Default), `NS`, `MX`, `ANY`, `SIG`

  Options

    +noall +answer                              # display answer section only
    +short                                      # only ip address
    -x ADDR                                     # reverse lookup

