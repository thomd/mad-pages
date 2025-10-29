
# rg(1)

Configuration is in `~/.ripgreprc`

## Output Options

    -I                # supress file paths
    -N                # suppress line numbers

## Options

    -i                # case insensitive search
    -s                # case sensitive search
    -z                # search in compressed files
    -t TYPE           # only search files matching TYPE
    -T TYPE           # do not search files matching TYPE
    --type-list       # show all supported file types
    -A NUM            # show NUM lines after each match
    -B NUM            # show NUM lines before each match
    -C NUM            # show NUM lines before and after each match
    -l                # only print the paths with at least one match
    -g GLOB           # include or exclude files
    --files           # print each file that would be searched
    -c                # only show the count of matching lines for each file
    -o                # print only matched parts of a line
    -w                # only show matches surrounded by word boundaries
    -M NUM            # don't print lines longer than this limit
    -v                # invert match
    -L, --follow      # follow symbolic links

    --no-ignore       # also search in git-ignored files
    --hidden, -.      # search also in hidden files
    --no-hidden       # do not search in hidden files
    -u                # is equivalent to `--no-ignore`
    -uu               # is equivalent to `--no-ignore --hidden`
    -uuu              # is equivalent to `--no-ignore --hidden --binary`

## Examples

    rg -i foo
    rg 'foo|bar|baz' -woNI | sort | uniq -c        # search for foo, bar or baz and count
    rg -- -foo                                     # search for -foo
    rg -t html -t css foobar                       # search in .html and .css files only for the word foobar
    rg -g *.css --files                            # print list of all .css files
    fd -e css -X rg color                          # print all colors in all css files
    rg "category-id=\".+?\"" catalog.xml -oN       # print only matched pattern

## Multiline Search

    echo 'apple\norange\nbanana\nkiwi' | rg --multiline --multiline-dotall 'orange.*kiwi'

# ripgrep - grep - rosetta stone

  list files containing `pattern` in current directory and subdirectories:

    rg -l pattern
    grep -rl pattern .
