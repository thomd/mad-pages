# Google Search

    "foo bar baz"                    # force an exact-match search with quotes
    foo AND bar                      # return only results related to both terms
    (foo OR bar) baz                 # results related to one of the search terms
    foo -bar                         # exclude terms or phrases with '-' operator
    "foo \* baz"                      # the '*' wildcard will be replaced by any word or phrase
    site:example.com foo             # search inside a single website
    filetype:pdf foo                 # find a specific file type
    foo 2016..2018                   # search for a range of numbers with '..' operator
    foo before:2020                  # results before a given year with 'before:' operator
    foo after:2020                   # results after a given year with 'after:' operator
    foo before:2020-01-31            # results before a given specific date with 'before:' operator

see also https://www.gwern.net/search

# googler(1)

    googler foo
    googler -n 5 foo                # show 5 results (default: 10)
    googler -V foo                  # show results from video section
    googler -c de                   # country specific search with TLD
    googler -l de                   # display in language

  Keys

    n, p                            # next, previous page
    f                               # first page
    o I1 I2 ...                     # open page with index I1, ... in browser
    c I                             # copy URL of index I to clipboard
    u                               # toggle URL expansion
    q, \<double enter>               # quit
