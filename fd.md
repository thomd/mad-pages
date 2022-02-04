# fd(1)

## Options

    -t TYPE                                     # f: file, d: directory, l: symlink, x: executable, e: empty
    -e EXT                                      # search for file extensions
    -p                                          # search within the entire pathname, not just the filename
    -s                                          # force case-sensitivity (default: ignore case unless an uppercase letter is in the pattern)

    -H, --hidden                                # search also in hidden files
    -I, -no-ignore                              # search also in ignored files
    -L, --follow                                # symbolic links are also traversed

    -x, --exec                                  # run an external command for each of the search results in parallel
    -X, --exec-batch                            # run the external command once, with all search results as arguments
    -l                                          # shortcut for `-X ls -alh`
    -E PATTERN                                  # exclude
    --changed-within TIME                       # filter by file modification time (newer than)

  The -x and -X option must come last, to have specific options of the external commands

## Usage

    fd PATTERN                                  # search for files matching "PATTERN"
    fd 'REGEX'                                  # search using regexp
    fd PATTERN FOLDER                           # search for files matching "PATTERN" within folder "FOLDER" 
    fd                                          # list all files recursively within the current folder
    fd . FOLDER                                 # list all files recursively within the given folder
    fd -e EXTENSION                             # search for file types
    fd -x COMMAND                               # run COMMAND for each found file

  Placeholder Syntax

    fd -x echo
    fd -x echo {/}                              # print basenames
    fd -e jpg -x convert {} {.}.png             # convert all jpg files to png files
    fd -e jpg -x mv {} {//}/foo{/}              # prefix all jpg files names with 'foo'

    {}      # documents/images/party.jpg
    {.}     # documents/images/party
    {//}    # documents/images
    {/}     # party.jpg
    {/.}    # party
 
## Examples

    fd -e mp3                                   # find all mp3 files in current dir
    fd -e mp3 . /                               # find all mp3 files everywhere. The '.' means arbitrary name
    fd '^.*rc$' /etc
    fd -e isml product ~/develop/               # search for isml template having "product" in filename
    fd -g 'test_*.py' -X vim -p                 # open all python tests in vim
    fd -e py -X rg foo                          # rip-grep for 'foo' in all python files
    fd -H -tf '^\.DS\_Store$' -X rm -i           # interactively delete all DS_Store files in current dir
    fd foo | as-tree                            # list search result as tree
    fd --changed-within \`now -s`                # find changed files since last call of 'now'
    fd --changed-within 30min                   # find changed files within the last 30min
    fd -IH -td ^venv$ ~/develop -X dua          # calculate disk usage of all venv folders
    fd -IHL -td ^rc$ ~                          # find all rc folders in ~
    fd -IHL -tf -p /rc/package.json$ ~          # find all 'package.json' files within a 'rc' folder
