# git-stash(1)

Stash the changes in a dirty working directory away

## stashing changes

    git stash
    git stash -p                                 # interactively specify changes included in this stash
    git stash -u                                 # include also untracked files
    git stash push -- file.txt                   # stash only a specific file
    git stash push -m "description"              # save stash with a description

## show stashed changes

    git stash list                               # list all stashes; alias git s
    git stash show                               # show files of first stash
    git stash show stash@{1}                     # show files of a specific stash; alias git stash show 1
    git stash show -p                            # show changes of first stash

## get back stashed changes

    git stash pop stash@{1}                      # apply a stash and drop from stack
    git stash pop                                # apply first stash and drop from stack
    git stash apply                              # apply first stash (and don't drop from stack)
    git stash apply stash@{1}                    # apply a stash from stack

## clear stashes

    git stash drop                               # drop latest stash
    git stash drop stash@{1}                     # drop a stash
    git stash clear                              # clear all stashes

## branching a stash

    git stash
    git stash branch feature                     # create and checkout a new branch 'feature' and apply stash@{0} to it
