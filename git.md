# git(1)

## Git Best Practices

  Find Branch which your current branch was branched off

    git reflog | grep "moving from"

  Commit Perspective

    git log COMMIT^..COMMIT -p                                # what changed on COMMIT ?

  File Perspective

    git diff COMMIT^...COMMIT -- FILE                         # How did FILE change on commit COMMIT ?

    git show BRANCH:FILE                                      # state of FILE in BRANCH
    git diff BRANCH..BRANCH -- FILE                           # compare FILE from two BRANCHES
    git checkout BRANCH -- FILE                               # checkout a file from BRANCH

    git log --follow -p -- FILE                               # history of a file
    tig FILE                                                  # history of a file using `tig`

    git reset @~ FILE && git commit --amend --no-edit         # uncommit a file

## Search History

    git log --diff-filter=D --summary                         # list all deleted files ever
    git log --summary -S PATTERN -- FILE                      # search the contents of deleted files
    git checkout COMMIT~1 -- FILE                             # restore a deleted file

## Stashing

    git stash
    git stash -p                        # interactively specify changes included in this stash
    git stash -u                        # include also untracked files
    git stash -k                        # stash only unstaged changes (--keep-index)
    git stash push -- FILE              # stash only a specific file

    git stash list                      # list all stashes; alias git s
    git stash show                      # show files of first stash
    git stash show stash@{1}            # show files of a specific stash

    git stash pop stash@{1}             # apply a stash and drop from stack
    git stash pop                       # apply first stash and drop from stack

    git stash clear                     # clear all stashes

