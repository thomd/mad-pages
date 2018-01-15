
# Git Flow

Initialize git flow (accepting all the defaults with `-d`)

    git flow init -d

## Feature

    git flow feature start 001             # create new branch features/001 based on develop
    git flow feature publish 001           # share: push the local branch and track the remote branch
    ... code ...
    git rebase -i develop                  # rebase all commits between develop and feature/001 (nice commit)
    git flow feature finish 001            # merge into develop and delete branch
    git push origin develop                # push to remote
    git push origin :feature/001           # delete remote feature branch 

Rebasing upstream is something you should be very careful about!

## Release

    git flow release start 1.2.0           # create new branch release/1.2.0 based on develop
    git flow release publish 1.2.0         # share: push the local branch and track the remote branch
    ... stabilize ...                      # stabilize relase (Changelog, Version, Pack, Bugs ...)
    git flow release finish 1.2.0          # merge into master, back-merge into develop, delete & tag 1.2.0
    git push origin develop

## Hotfix

    git pull origin master
    git flow hotfix start 1.2.1            # create new branch hotfix/1.2.1 based on master
    ... fix ...                            # fix relase (Changelog, Version, Bug ...)
    git flow hotfix finish 1.2.1           # merge into master, back-merge into develop, delete & tag 1.2.1
    git push origin master --tags 1.2.1    # ... then deploy using Git Panel
    git push origin develop

## Troubleshooting

If you get "There is an existing hotfix branch (1.12.x). Finish that one first.", delete local branch first.
