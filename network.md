# Network

## Print listening ports and programs

    netstat -an | grep LISTEN                      # List listening ports
    sudo lsof -i -P | grep LISTEN                  # List listening ports and programs
    nc -v -z localhost 1-1023

## What is the IP of my Nameserver?

    cat /etc/resolv.conf

