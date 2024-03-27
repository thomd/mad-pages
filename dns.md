# DNS

## hosts file

    sudo vim /etc/hosts                    # assign hostname to IP
    sudo dscacheutil -flushcache           # flush DNS cache

  In Chrome, open `chrome://net-internals/#dns`

## dig(1)

  Syntax

    dig \<options> @\<nameserver> \<name> \<type>

  with type: `A` (Default), `NS`, `MX`, `ANY`, `SIG`

  Options

    +noall +answer                              # display answer section only
    +short                                      # only ip address
    -x ADDR                                     # reverse lookup

