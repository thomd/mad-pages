
# vim(1)

    vim large.xml "+syntax off"

## Vim's Grammar

    [operator][count][motion]

Examples

    v3w                            # select three words
    cs])                           # change surrounding brackets to parantheses

## Commands

    d0                             # delete before cursor position
    100i-\<ESC>                     # write 100 dashes
    yypVr-                         # underline text with dashes

## Execute Shell Commands in Vim

    :% ! json2yml %                # convert json to yml
    :r ! date                      # insert date
    :% ! js-beautify               # format javascript

## Modeline

    # vim:ft=bash                  # use bash syntax highlighting
    # vim:nospell                  # no spell checking
    # vim:nospell:nowrap:tw=0

## Record a Macro

    qa                             # start recording (or any other lower case character to name the macro)
    ... edit ...
    q                              # stop recording
    @a                             # replay
    N@a                            # replay N times ( VG:normal @a to replay until end of buffer)

