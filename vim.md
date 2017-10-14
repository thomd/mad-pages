
# vim(1)

## Vim's Grammar

    [operator][count][motion]

Examples

    v3w                     # select three words
    cs])                    # change surrounding brackets to parantheses

## Commands

    d0                      # delete before cursor position
    100i-\<ESC>              # write 100 dashes
    yypVr-                  # underline text with dashes

## Execute Shell Commands in Vim

    :% ! json2yml %         # convert json to yml
    :r ! date               # insert date
