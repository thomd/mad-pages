# vd(1)

    vd                                                 # browse current directory and sub directories
    vd data.zip                                        # interactively open a zip file
    vd -b input.csv -o output.json                     # convert from csv to json
    ls -l | vd -f fixed --skip 1 --header 0            # parse the output of ls -l into usable data
    vd --csv-delimiter ";" data.csv                    # use ; as delimiter (default is ,)

## Commands

    F        # frequency table
    I        # descriptive statistics
    C        # open columns sheet
    S        # open sheets sheet
    Enter    # open row sheet
    T        # transpose sheet

    _        # toggle column width
    /        # search in current column
    g/       # search in all columns
    c        # find column name by regex
    -        # hide column

    s        # select a row
    u        # unselect a row
    gt       # toggle all rows between selected / unselected
    ,        # select all rows matching current cell
    |        # select all rows matching a regex
    "        # create new sheet of selected rows

    za       # add a new blank column
    :        # create new column by splitting current column on regex
    =        # bring up the prompt `new column expr=`
    Ctrl ^   # toggle between current and previous sheet
    gY       # copy selected rows to clipboard

    e        # edit (in memory) current cell
    ^        # rename current column header
    Ctrl s   # save current sheet to filename

    #        # set column type integer
    %        # set column type float
    @        # set column type date
    ~        # set column type text
