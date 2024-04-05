# zip(1)

    zip -e protected.file.zip file.txt                   # create a password protected zip archive of a file
    zip -er protected.folder.zip folder/                 # create a password protected zip archive of a folder
    zip -eur protected.folder.zip folder/                # update existing password protected zip archive

# unzip(1)

    unzip -l protected.zip                               # list, but do not unzip
    unzip protected.zip
