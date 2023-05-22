
# vim(1)

    vim large.xml "+syntax off"
    vim -                                         # read text from stdin, e.g. `ls -al | vim -`
    vim -u NONE                                   # ignore `~/.vimrc`
    vim -p \`git status -su | cut -d ' ' -f2-`     # open changed files

Vim's Grammar

    [operator][count][motion]

    v3w                            # select three words
    cs])                           # change surrounding brackets to parantheses

## Useful Commands

    d0                             # delete before cursor position
    100i-\<ESC>                     # write 100 dashes
    yypVr-                         # underline text with dashes
    :w !sudo tee %                 # save a file edited without the needed permissions

## Execute Shell Commands in Vim

    :% ! json2yml %                # convert json to yml
    :r ! date                      # insert date
    :% ! js-beautify               # format javascript
    :% ! xmlstarlet fo             # format xml
    :% ! paste -sd,                # join lines with a comma

## Modeline

Add modelines in files at the end or the begining

    # vim:ft=bash                  # use bash syntax highlighting
    # vim:nospell                  # no spell checking
    # vim:nospell:nowrap:tw=0

## Record a Macro

    qa                             # start recording (or any other lower case character to name the macro)
    ... edit ...
    q                              # stop recording
    @a                             # replay
    N@a                            # replay N times ( VG:normal @a to replay until end of buffer)

## Marks

    ma                             # set mark `a`

    :marks                         # list all current marks
    ''                             # position before the latest jump
    '.                             # last edit
    'a                             # jump to mark

    d'a                            # delete all lines from the cursor position to mark a
    :'a,'bd                        # deletes lines from mark a to mark b, inclusive
    :'a,'bw file.txt               # writes lines from mark a to b to file.txt
    :'a,'bw >> file.txt            # append lines from mark a to b to file.txt

## Multiselect

    ctrl n                         # start selecting words
    N / n                          # select previous / next word
    q                              # skip current selection
    Q                              # remove current selection
    [ / ]                          # jump to previous / next word
    shift arrow                    # select one character

## Options

  Editor Options

    :set nu                        # line numbers
    :set rnu                       # relative line numbers
    :set ic                        # ignore case in searches
    :set is                        # enable incremental search
    :set wrap                      # word wrap
    :set tw=160                    # text width for automatic line break (no line break: :set tw=0)
    :set spell                     # enable spell checker

File Options

    :set ft=\<lang>                 # set file type for syntax highlighting (shortcut: :setf <lang>)
    :set ff=unix|dos               # set file format: DOS line endings (0D0A) to UNIX line endings (0A)
    :set fenc=utf-8                # change file encoding to UTF-8. Alternatively use `iconv`
    :set bomb                      # add UTF-8 Byte Order Mark


