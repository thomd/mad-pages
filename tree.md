# tree(1)

Options

    -a                                 # all files are printed (even dot-files)
    -d                                 # list directories only
    -L \<level>                         # max display depth of the directory tree
    -h                                 # print the size of each file but in a more human readable way
    -p                                 # print permissions of each file
    -P \<pattern>                       # list  only  those  files  that match the wild-card pattern
    -I \<pattern>                       # do not list those files that match the wild-card pattern

Examples

    alias t='tree -a -I ".git|.svn"'   # handy short cut
    ls -R                              # simulate tree
