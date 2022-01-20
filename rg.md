
# rg(1)

ripgrep

## Options

    -i                # case insensitive search
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
    -o                # print only matches parts of a line
    -I                # never print the file path with the matched lines
    -N                # suppress line numbers
    -w                # only show matches surrounded by word boundaries
    -M NUM            # don't print lines longer than this limit
    -v                # invert match
    --no-ignore       # also search in git-ignored files
    --hidden          # search also in hidden files

## Configuration

Configuration in `~/.ripgreprc`

    # don't let ripgrep vomit really long lines to my terminal, and show a preview.
    --max-columns=160
    --max-columns-preview

    # custom types
    --type-add
    html:*.isml

    # using glob patterns to include/exclude files or folders
    --glob=!node_modules/*
    --glob=!.git/*

    # because who cares about case!?
    --smart-case

    # of course we search in hidden files
    --hidden

## Examples

    rg -i foo
    rg 'foo|bar|baz' -woNI | sort | uniq -c     # search for foo, bar or baz and count
    rg -- -foo                                  # search for -foo
    rg -t html -t css foobar                    # search in .html and .css files only for the word foobar
    rg -g *.css --files                         # print list of all .css files
    fd -e css -X rg color                       # print all colors in all css files

## Multiline Search

    echo 'apple\norange\nbanana\nkiwi' | rg --multiline --multiline-dotall 'orange.*kiwi'

# ripgrep - grep - rosetta stone

  list files containing `pattern` in current directory and subdirectories:

    rg -l pattern
    grep -rl pattern .
