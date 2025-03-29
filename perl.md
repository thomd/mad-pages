# perl(1)

## Options

    -i                          # edit file in place
    -ibak                       # edit file in place and make '*.bak' backup
    -e CODE                     # one line of program (multiple '-e' are allowed)
    -n                          # assume 'while(<>){...}' loop around program
    -p                          # assume loop like '-n' but print line, like 'sed'
    -w                          # write warnings

## Perl Oneliners

    cat /usr/share/dict/words | tr 'A-Z' 'a-z' | perl -nle 'print for /\b[a-z]e[a-z]se\b/g'         # find english word matching ?e?se
    perl -pi -w -e 's/foo/bar/g;' *.txt                                                             # search and replace in multiple 'txt' files
    tail -f | perl -pe 's/keyword/\e[1;31;43m$&\e[0m/g'                                             # color 'keyword' in stdout stream
