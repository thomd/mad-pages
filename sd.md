# sd(1)

find & replace

## Options

    -F                # treat FIND and REPLACE_WITH args as literal strings
    -f                # Regex flags. May be combined like `-f mc`
                      #       c - case-sensitive
                      #       e - disable multi-line matching
                      #       i - case-insensitive
                      #       m - multi-line matching
                      #       s - make '.' match newlines
                      #       w - match full words only
    -p                # preview changes (dry-run)

## Examples

    sd 'foo' 'bar' file.txt                                 # inline-replace foo with bar in file.txt
    fd -e json . path/to/project -x sd 'foo' 'bar'          # inline-replace foo with bar in all json files
    echo 'foo    ' | sd '\s+$'                              # trim trailing whitespace
