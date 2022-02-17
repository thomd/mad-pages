
# vim(1)

    vim large.xml "+syntax off"
    vim -                                  # read text from stdin, e.g. `ls -al | vim -`
    vim -u NONE                            # ignore `~/.vimrc`

Vim's Grammar

    [operator][count][motion]

    v3w                            # select three words
    cs])                           # change surrounding brackets to parantheses

Common Commands

    d0                             # delete before cursor position
    100i-\<ESC>                     # write 100 dashes
    yypVr-                         # underline text with dashes
    :w !sudo tee %                 # save a file edited without the needed permissions

Execute Shell Commands in Vim

    :% ! json2yml %                # convert json to yml
    :r ! date                      # insert date
    :% ! js-beautify               # format javascript

Modeline

    # vim:ft=bash                  # use bash syntax highlighting
    # vim:nospell                  # no spell checking
    # vim:nospell:nowrap:tw=0

Record a Macro

    qa                             # start recording (or any other lower case character to name the macro)
    ... edit ...
    q                              # stop recording
    @a                             # replay
    N@a                            # replay N times ( VG:normal @a to replay until end of buffer)

Marks

    :marks                         # list all current marks
    ''	                           # position before the latest jump
    '.                             # last edit
    'a - 'z                        # lowercase marks, valid within one file

    d'a                            # delete all lines from the cursor position to mark a
    :'a,'bd                        # deletes lines from mark a to mark b, inclusive
    :'a,'bw file.txt               # writes lines from mark a to b to file.txt
    :'a,'bw >> file.txt            # append lines from mark a to b to file.txt
