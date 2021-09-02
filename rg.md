
# rg(1)

ripgrep

## Options

    -i                                          # Case insensitive search
    -z                                          # Search in compressed files
    -t TYPE                                     # Only search files matching TYPE
    -T TYPE                                     # Do not search files matching TYPE
    --type-list                                 # Show all supported file types
    -A NUM                                      # Show NUM lines after each match
    -B NUM                                      # Show NUM lines before each match
    -C NUM                                      # Show NUM lines before and after each match
    -l                                          # Only print the paths with at least one match
    -g GLOB                                     # Include or exclude files
    --files                                     # Print each file that would be searched
    -c                                          # Only show the count of matching lines for each file
    -o                                          # Print only matches parts of a line
    -I                                          # Never print the file path with the matched lines
    -N                                          # Suppress line numbers
    -w                                          # Only show matches surrounded by word boundaries
    -M NUM                                      # Don't print lines longer than this limit

## Examples

    rg -i foo
    rg 'foo|bar|baz' -woNI | sort | uniq -c     # search for foo, bar or baz and count
    rg -- -foo                                  # search for -foo
    rg -t html -t css foobar                    # search in .html and .css files only for the word foobar
    rg -g *.css --files                         # print list of all .css files
    fd -e css -X rg color                       # print all colors in all css files

## Multiline Search

    echo 'apple\norange\nbanana\nkiwi' | rg --multiline --multiline-dotall 'orange.*kiwi'
