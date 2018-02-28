# tar(1)

Create

    tar -cvf file.tar folder/                  # create tar
    tar -czvf file.tar.gz folder/              # create tar.gz
    tar -cvf - folder | gpg -c > file.tar      # tar and encrypt a folder
    ls | tar -cf files.tar -T -                # tar files from stdin

Check

    tar -df file.tar                           # check tar
    tar -tf file.tar                           # list contents of tar

Extract

    tar -xvf file.tar                          # extract tar
    tar -xzvf file.tar.gz                      # extract tar.gz
    tar -xvf file.tgz                          # extract tgz
