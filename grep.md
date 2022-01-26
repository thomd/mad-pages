# grep(1)

## Options

    -h                                              # do not show filename
    -i                                              # no case
    -r                                              # recursive
    -o                                              # show only mattching word of the line
    -v                                              # invert match
    -l                                              # display only the file names which matches the given pattern

## Examples

    grep -r foo .                                   # grep for 'foo' in current folder
    grep -e '-X'                                    # use -e when pattern has a leading '-'
    grep -v '^$' file                               # remove blank lines
    ps ax | grep ssh | grep -v grep                 # list ssh processes without grep process
    tail -f | grep -E 'error|'                      # colorize 'error' in tail
    grep --color='auto' -P -n "[\x80-\xFF]" file    # grep for non-ASCII Characters
    cat file1 | grep -f - file2                     # grep for pattern from file1 in file2
    grep -o '.' file.txt | sort | uniq -c           # letter distribution of all words in file.txt
