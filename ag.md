
# ag(1)

The Silver Searcher

## Usage

`ag '^ba(r|z)$'` find files containing a regular expression

`ag -g FILENAME` find files with a file-name matching "FILENAME"

`ag -l PATTERN` find files containing "PATTERN", but only list the filenames

`ag -i PATTERN` find files containing "PATTERN" case-insensitively

`ag -o PATTERN` find files containing "PATTERN", but print only the match, rather than the whole line

`ag PATTERN -G FILENAME` find "PATTERN" in files with a name matching "FILENAME"

`ag --hidden PATTERN` search hidden files. This option obeys ignore files

`ag -w PATTERN` only match whole words

`ag -z PATTERN` search contents of compressed files

## Filetypes

`ag --list-file-types`

`ag --js PATTERN` find files containing "PATTERN" in JavaScript files
