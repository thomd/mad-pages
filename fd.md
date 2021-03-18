# fd(1)

## Options

    -t TYPE                                     # f: file, d: directory, l: symlink, x: executable, e: empty
    -e EXT                                      # search for file extensions
    -H, --hidden                                # searchalos in hidden files
    -I, -no-ignore                              # search also in ignored files
    -x, --exec                                  # run an external command for each of the search results in parallel
    -X, --exec-batch                            # run the external command once, with all search results as arguments
    -l                                          # shortcut for -X ls -alh
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

    {}      # documents/images/party.jpg
    {.}     # documents/images/party
    {//}    # documents/images
    {/}     # party.jpg
    {/.}    # party
 
## Examples

    fd -e mp3                                   # find all mp3 files in current dir
    fd -e mp3 . /                               # find all mp3 files everywhere
    fd '^.*rc$' /etc
    fd -e isml product ~/develop/               # search for isml template having "product" in filename
    fd -g 'test_*.py' -X vim -p                 # open all python tests in vim
    fd -H '^\.DS\_Store$' -tf -X rm -i           # interactively delete all DS_Store files in current dir
    fd foo | as-tree                            # list search result as tree
    fd --changed-within \`now -s`                # find changed files since last call of now

