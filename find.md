
# find(1)

    find . *jpg -delete                                # delete all jpg file
    find . -type f -mtime +30 -delete                  # delete files in folder older than 30 days
    find . -iname "file.zip" -exec md5sum {} \;        # calculate md5 hash of zip files
    find . -name "*.zip" -exec cp {} ../zips/ \;       # find all zip files and copy into a parent folder

Grep something within a large list of files:

    while read file; do grep -E regex-pattern $file; done < <(find . -name "*.log")

  or

    ack -C 0 pattern
