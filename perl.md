# perl(1)

    cat /usr/share/dict/words | tr 'A-Z' 'a-z' | perl -nle 'print for /\b[a-z]e[a-z]se\b/g'         # find english word matching ?e?se
