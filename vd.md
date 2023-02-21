# vd(1)

    vd                                                 # browse current directory and sub directories
    vd data.zip                                        # interactively open a zip file
    vd -b input.csv -o output.json                     # convert from csv to json
    ls -l | vd -f fixed --skip 1 --header 0            # parse the output of ls -l into usable data
    vd --csv-delimiter ";" data.csv                    # use ; as delimiter (default is ,)
    curl -sL https://git.io/IRIStsv | vd -f tsv        # open tab-delimiter file

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
    a        # add a new blank row
    ga \<N>   # add \<N> new blank rows
    :        # create new column by splitting current column on regex, e.g. split 01/01/2023 by / to get three new columns
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

    .        # plot numerical data

## VisiData Best Practices

format date column from 'mm/dd/yyyy' to 'mm/yyyy'

    :  /                                    # split 'date' into three new columns 'date\_re0', 'date\_re1' and 'date\_re2'
    -                                       # delete 'date\_re1' column
    =  date\_re1 + date\_re2                  # concat to a new column





