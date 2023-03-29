# qsv(1)



# csvkit(1)

## Options

    -d DEL                                # delimiting character of the input CSV file
    -q CHAR                               # character used to quote strings
    -l                                    # insert a column of line numbers
    -K LINES                              # skip number of lines before the header row (e.g. comments, copyright notices)
    -H                                    # create default headers a,b,c,... if data has no header row
    -S                                    # ignore whitespace immediately following the delimiter

## Input

    csvsql --db "sqlite:///data.db" --tables "data" --insert data.csv   # import CSV into SQL database
    sql2csv --db "sqlite:///data.db" --query "select * from data"       # output SQL-queries as CSV
    in2csv data.xlsx > data.csv                                         # convert tabular data formats into CSV

## Processing

    csvcut -n data.csv                                                  # print column names and indices
    csvcut -n data.csv | cut -c6-                                       # print only column names
    csvcut -c 2,5-8 data.csv                                            # print given columns
    csvcut -C 2,5-8 data.csv                                            # print all except given columns
    csvcut -c 2,5-8 -x data.csv                                         # after cutting, delete rows which are empty
    csvcut -c county,name data.csv | csvlook | head
    csvcut -c 2 data.csv | sed 1d | sort | uniq                         # print unique values of a column

    csvclean data.csv                                                   # fix common errors. Writes \*\_out.csv and \*\_err.csv
    csvclean -n data.csv                                                # dry-run fix common errors
    daff data.csv data_out.csv                                          # diff two csv files

    csvgrep -c 1 -m foo data.csv                                        # print rows containing 'foo' in first columnn
    csvgrep -c 1 -r "($i)foo" data.csv                                  # print rows containing 'foo' case-insensitive
    csvgrep -c 1 -r "^A" data.csv                                       # print rows with values startingn with A in first column
    csvgrep -c 1 -r "^$" -i data.csv                                    # print rows with non-empty cell inn first column

    csvjoin -c 1 a.csv b.csv                                            # inner join
    csvjoin -c 1 --outer a.csv b.csv                                    # outer join

    csvsort -c 1,3 data.csv                                             # sort csv by column 1 and 3
    csvsort -c 3 -r data.csv                                            # sort reverse by column 3

    csvlook data.csv | less -S                                          # print as markdown-compatible, fixed-width table

    csvformat -D "|" data.csv                                           # convert to a pipe-delimited file
    csvformat -U 2 data.csv                                             # quoute non-numeric columns

    csvjson data.csv                                                    # print as JSON
    csvjson -k foo data.csv                                             # print as JSON with column 'foo' as key

    csvstat data.csv                                                    # statistical data summary
    csvstat -c 5 data.csv                                               # statistical data summary of column 5
    csvstat --unique data.csv                                           # print number of unique values for each column

# csvfix(1)

## Data Info

    csv echo -sep ';' data.csv                      # print data.csv having ; as field separator
    csv stat data.csv                               # print "<filename>;<number-of-lines>;<min-fields>;<max-fields>"

## Transform Data

    csv echo -sep ';' data.csv                      # print data.csv having ; as field separator
    csv echo -sep ';' -osep ',' data.csv            # change delimiter from ; to ,
    csv rmnew data.csv                              # replace all newline characters with a space

## Selecting Columns

    csv order -f 1,3 data.csv                       # print column 1 and 3
    csv order -f 1:3 data.csv                       # print column 1, 2 and 3
    csv order -xf 1 data.csv                        # print all columns except column 1
    csv order -rf 1 data.csv                        # print last column (count from end)
    csv order -fn field1 data.csv                   # print column with name field1
    csv order -fn field1, field2 data.csv           # print column with name field1 and field2
    csv exclude -f 3,4 data.csv                     # exclude column 3 and 4
    csv exclude -rf 1,2 data.csv                    # exclude last two columns (reverse order)
    csv exclude -f 2:8 data.csv                     # exclude column 2 until 8
    csv truncate -n 6 data.csv                      # truncate to 6 records by removing rightmost fields

## Selecting Rows

    csv head -n 3 data.csv                          # print first three record
    csv tail -n 3 data.csv                          # print last three record
    csv find -f 2 -s '0' data.csv                   # find all rows with an '0' in the second column
    csv remove -f 1 -e '[0-9]' data.csv             # remove all rows with an '0' in the second column
    csv remove -l 12 data.csv                       # remove all rows with at least one field of length 12

## Diff Data

    csv diff data1.csv data2.csv                    # print diff of two csv files
    csv diff -ic -is data1.csv data2.csv            # diff (ignore case and leading/trailing space)

## Print Data

    csv ascii_table data.csv                        # print data in table
    csv ascii_table -h @ data.csv                   # consider first line as header
    csv sort -f 3:D,2 data.csv                      # sort third column descending and then second ascending

## Examples

  Print column 4 if column 2 contains empty values:

    csv rmnew data.csv | csv find -if 'len($2)==0' | csv order -f 4 

  Print column index:

    head -n 1 data.csv | tr ';' '\n' | nl

  Print columns 2, 4 and 5 and a row number:

    csv order -sep ";" -f 2,4:5 data.csv | csv sequence -n 0
