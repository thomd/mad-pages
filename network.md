# Network

## Print listening ports and programs

    netstat -an | grep LISTEN                      # List listening ports
    sudo lsof -i -P | grep LISTEN                  # List listening ports and programs

## What is the IP of my Nameserver?

    cat /etc/resolv.conf

