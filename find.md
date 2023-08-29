
# find(1)

Examples

    find . -type f -name "a*"                                                     # list file paths
    find * -type f -name "a*"                                                     # list file names
    
    find . -name "*.jpg" -delete                                                  # delete all jpg file
    find . -type f -mtime +30 -delete                                             # delete files in folder older than 30 days
    find . -iname "file.zip" -exec md5sum {} \;                                   # calculate md5 hash of zip files
    find . -name "*.zip" -exec cp {} ../zips/ \;                                  # find all zip files and copy into a parent folder
    find . -name "\*.jpg" -o -name "*.png"                                         # find PNG or JPG images
    find . -name "package.json" -not -path "\*/node_modules/*"                     # exclude sub folder
    while read f; do grep -E \<pattern> $f; done \< \<(find . -name "*.log")         # grep <pattern> within a large list of log files


