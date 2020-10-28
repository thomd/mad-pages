
# sed(1)

    sed -n 10,20p file                    // print line 10-20
    sed /pattern/d file                   // delet all line matching pattern
    ed /^$/d file                         // remove all blank line from file
    sed 10,20d file                       // remove line 10 to 20 from file
    sed 1d file                           // remove first line from file
    sed \$d file                          // remove last line from file
    sed 1!d file                          // remove all but the first line from file
