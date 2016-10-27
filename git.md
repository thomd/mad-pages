
# what have I done in my branch?

Supposed I'm in branch `development` which was branched off of `master`

    git log master..

# git-log(1)

    git checkout develop
    git log                          # all commits of develop (full history)
    git log master                   # all commits of master (full history)
    git log master..                 # commits in develop since last merge
    git log ..master                 # commits in master since last merge
    git log master...                # commits in develop since branch creation

    git checkout develop
    git fetch
    git log ..origin/develop         # commits in origin/develop since last merge
    git log origin/develop..         # commits in develop since last merge

# What is in the repository?

    git ls-tree -r --name-only HEAD

# How to remove a just commited file/folder

    git ls-tree -r --name-only HEAD
    git rm <file>
    git rm -r <folder>
    git commit --amend
