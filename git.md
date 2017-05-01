
# Git Best Practices

## What's behind and ahead origin/master?

    git fetch
    git branch -vv

  behind:

    git log ..origin/master
    git diff ...origin/master

  ahead:

    git log origin/master..
    git diff origin/master...


## What files are in my repository?

    git ls-tree HEAD -r --name-only


## Find largest file in my repository

    git ls-tree HEAD -l -r | sort -n -k4 | tail -1


## How to remove a just committed file/folder

    git ls-tree -r --name-only HEAD
    git rm \<file>
    git rm -r \<folder>
    git commit --amend


## Restore a deleted file

    git log -- path/to/filename
    git revert \<sha1>


## Restore a change from the past

    git log -S"foo" -p
    git revert -n \<sha1>


## Drop everything since last push

    git reset --hard origin/master


## Restore old state of a specific file

    git log
    git checkout \<sha1> -- path/to/file


## I did something terribly wrong - use time machine

  Get a list of every thing you've done in git

    git reflog

  and find the commit _before_ you broke everything

    git reset HEAD@{n}


## Change message of last commit

    git commit --amend


## Make small change in last commit

    vim file
    git add .
    git commit --amed


## I accidentally committed something to master that should have been on a _brand new branch_

    git branch new-branch
    git reset HEAD~ --hard
    git checkout new-branch


## I accidentally committed to the wrong branch

    git reset HEAD~ --soft
    git stash
    git checkout correct-branch
    git stash pop
    git add .
    git commit -m "new commit message"


## Why is my file ignored?

    git check-ignore -v path/to/file

