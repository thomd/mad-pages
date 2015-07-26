# lsof(1)

List all IPv4 network files

    sudo lsof -i4

Find listening ports

    lsof -Pnl +M -i4

List all network connections

    lsof -i

Find which program is using port 80

    lsof -i TCP:80
    lsof -i:80

List all processes accessing a particular file/directory

    lsof /path/to/file

List all files open for a particular user

    lsof -u \<username>

List all files/network connections a given process is using

    lsof -c \<command-name>

