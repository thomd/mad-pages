
# Git Flow

Initialize git flow (accepting all the defaults with `-d`)

    git flow init -d

## Feature

    git flow feature start 001          # create new branch features/001 based on develop
    git flow feature publish 001        # [OPTIONAL] push the local branch and track the remote branch
  ... code ...
    git flow feature finish 001         # merge to develop with --no-ff, delete local branch
    git push origin develop             # push develop to remote
    git push origin :feature/001        # [OPTIONAL] delete remote feature branch

## Release

    git flow release start 1.2.0        # create new branch release/1.2.0 based on develop
    git flow release publish 1.2.0      # [OPTIONAL] push the local branch and track the remote branch
  ... stabilize ...                     # stabilize release (VERSION, CHANGELOG, Pack, Bugs ...)
    git flow release finish 1.2.0       # merge to master and develop with --no-ff, tag 1.2.0, delete branch
    git push origin develop
    git push origin master
    git push origin master --tags
    git push origin :release/001        # [OPTIONAL] delete remote feature branch

## Hotfix

    git pull origin master
    git flow hotfix start 1.2.1         # create new branch hotfix/1.2.1 based on master
    git flow hotfix publish 1.2.1       # [OPTIONAL] push the local branch and track the remote branch
  ... fix ...                           # fix critical bug
    git flow hotfix finish 1.2.1        # merge to master and develop with --no-ff, tag 1.2.1, delete branch
    git push origin develop
    git push origin master
    git push origin master --tags
    git push origin :hotfix/001         # [OPTIONAL] delete remote feature branch

