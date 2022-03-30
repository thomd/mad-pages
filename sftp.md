# sftp(1)

    sftp user@host_or_ip

Commands

    pwd                                # remote working directory
    lpwd                               # local working directory

    ls [-al]                           # list remote content
    lls                                # list local content

    cd PATH                            # change remote directory
    lcd PATH                           # change local directory

    get FILE                           # download remote file to local
    get FILE NEW_NAME                  # download remote file to local with new name
    get -r DIR                         # download remote directory to local
    get -p FILE                        # download remote file and keep permissions

    df -h                              # check if the is enough space for upload
    put FILE                           # upload local file to remote
    put -r DIR                         # upload local directory to remote

    !                                  # drop into a local shell
    exit                               # quit local shell and return to ftp session

    bye                                # quit sftp
