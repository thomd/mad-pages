# git(1)

## Find Merged Pull Requests of a JIRA Ticket

    git log develop --oneline --no-decorate --grep "Merged PR" | rg JIRA_ID

## Find Branch which your current branch was branched off (goes back only ~90 days)

    git reflog | grep "checkout: moving from" | grep BRANCH

## What was changed?

    git log A^..A -p                                          # what was changed in commit A ?

    git diff A^...A -- FILE                                   # How did FILE change on commit COMMIT ?

## Files

    git show BRANCH:FILE                                      # show state of FILE in BRANCH
    git show :FILE                                            # show state of FILE in current branch
    git diff BRANCH..BRANCH -- FILE                           # compare FILE from two BRANCHES
    git checkout BRANCH -- FILE                               # checkout a file from BRANCH

    git log --follow -p -- FILE                               # history of a file
    tig FILE                                                  # history of a file using `tig`

    git reset @~ FILE && git commit --amend --no-edit         # uncommit a file

## Diff

    git diff --color-moved=no                                 # do not show moved lines of code with different color

## Empty Commit

    git commit --allow-empty -m "trigger Azure pipeline" --no-verify

## Create Patch File

    git diff --no-color > my.patch

    git apply --check my.patch                                # test before actually applying it
    git apply my.patch

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

