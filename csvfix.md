
# csvfix(1)

    csvfix command-1 data.csv | csvfix command-2       # piping of multiple commands
    csvfix data1.csv data2.csv                         # processing multiple csv files
    csvfix order -sep ';' -f 1 data.csv                # set separator (default: ',')

  order

    csvfix order -f 1 data.csv                         # print column 1
    csvfix order -f 4:6 data.csv                       # print column 4 to 6
    csvfix order -f 1,4:6 data.csv                     # print column 1 and 4 to 6
    csvfix order -xf 1 data.csv                        # print all columns except column 1
    csvfix order -rf 1 data.csv                        # print last column (count from end)
    csvfix order -fn field1 data.csv                   # print column with name field1
    csvfix order -fn field1,field2 data.csv            # print column with name field1 and field2

  head

    csvfix head -n 1 data.csv                          # print first record (head)

  ascii table

    csvfix ascii_table data.csv                        # print data in table
    csvfix ascii_table -h @ data.csv                   # consider first line as header

  find / remove

    csvfix find -f 2 -s '0' data.csv                   # find all rows with an '0' in the second column
    csvfix remove -f 1 -e '[0-9]' data.csv             # remove all rows with an '0' in the second column
    csvfix remove -l 12 data.csv                       # remove all rows with at least one field of length 12

  rmnew

    csvfix rmnew data.csv                              # replace all newline characters with a space
    csvfix rmnew -s ',' data.csv                       # replace all newline characters with a comma character
    csvfix rmnew -x data.csv                           # remove all data following the first newline character

  sort

    csvfix sort -f 3:D,2 data.csv                      # sort third column descending and then second ascending
