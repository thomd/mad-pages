# vd(1)

    vd                                                 # browse current directory and sub directories
    vd data.zip                                        # interactively open a zip file
    vd -b input.csv -o output.json                     # convert from csv to json
    ls -l | vd -f fixed --skip 1 --header 0            # parse the output of ls -l into usable data
    vd --csv-delimiter ";" data.csv                    # use ; as delimiter (default is ,)
    curl -sL https://git.io/IRIStsv | vd -f tsv        # open tab-delimiter file
    echo "1,2" | vd --header 0                         # do NOT use first row as header

## Commands

    F        # frequency table
    I        # descriptive statistics
    C        # open columns sheet
    S        # open sheets sheet
    Enter    # open row sheet
    T        # transpose sheet
    v        # toggle multiline mode for line wrap

    _        # toggle column width
    /        # search in current column
    g/       # search in all columns
    c        # find column name by regex
    -        # hide column

    s        # select current row
    u        # unselect current row
    gu       # unselect all rows
    t        # toggle selection of current row
    gt       # toggle selection of all rows
    ,        # select all rows matching current cell
    |        # select all rows matching a regex in current colum
    g|       # select all rows matching a regex in any visible column
    "        # create new sheet of selected rows

    za       # add a new blank column
    a        # add a new blank row
    ga \<N>   # add \<N> new blank rows
    :        # create new column by splitting with `split regex:`
    =        # create new column by expression `new column expr=`
    Ctrl ^   # toggle between current and previous sheet
    gY       # copy selected rows to clipboard

    e        # edit (in memory) current cell
    ^        # rename current column header
    Ctrl s   # save current sheet to filename

    #        # set column type integer
    %        # set column type float
    @        # set column type date
    ~        # set column type text

    zY       # copy value of current cell

    .        # plot numerical data

## VisiData Best Practices

  Extract pattern and create new column

    ;  ([0-9]{4})                           # create new colum containing all 4-digit numbers within current column
    (                                       # expand column

  Format date column from 'mm/dd/yyyy' to 'mm/yyyy':

    :  /                                    # split 'date' into three new columns 'date\_re0', 'date\_re1' and 'date\_re2'
    -                                       # delete 'date\_re1' column
    =  date\_re1 + date\_re2                  # concat to a new column

  Select Data with Frequency Tables:

    F                                       # to show frequency table
    Enter                                   # on a row to see the source rows for that value
    g '                                     # to freeze the sheet, converting it to a regular sheet for further manipulation

  Find all Emails not post-fixed with '.invalid':

    |  \.invalid$
    gt
    "

  Histogram over Date

    @                                       # convert y-axis to date
    !                                       # and set as key column
    F                                       # frequnecy table
                                            # select 'count' column - or mae existing count column numeric with `#`
    .                                       # create graph
