
# git-log(1)

    git checkout develop
    git log                          # all commits of develop (full history)
    git log master                   # all commits of master (full history)
    git log master..                 # commits in develop since branching; shorthand for git log ^master develop
    git log ..master                 # commits in master since branching; shorthand for git log master ^develop
    git log origin/master..          # commits in origin/master since last pull
    git log ..origin/master          # commits in master since last push
    git log master...                # commits in develop and master since branching
