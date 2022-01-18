# slugify(1)

Example: `Ghost File.txt` -> `ghost_file.txt`

    slugify -n *                         # dry run on all files of current directory
    slugify -n "Ghost File.txt"          # test filenames that don't exist
    slugify -iad *
    slugify *.txt
    
    slugify -u                           # underscore -> space
    slugify -t                           # dash -> space
    slugify -d                           # space -> dash
    slugify -c                           # space space ... -> space
