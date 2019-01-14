
# Git Best Practices

## What's behind and ahead origin/master?

    git fetch --all

  behind:

    git log ..origin/master
    git diff ...origin/master

  ahead:

    git log origin/master..
    git diff origin/master...


## What have I done in my branch?

    git log master..
    git diff master...


## What files are in my repository?

    git ls-tree HEAD -r --name-only


## Find largest file in my repository

    git ls-tree HEAD -l -r | sort -n -k4 | tail -1


## How to remove a committed file

  remove from index but not from the working tree

    git rm --cached \<file>

  remove from index

    git rm \<file>
    git rm -r \<folder>


## Print file change history

    git log --follow -p -- \<file>


## Find and restore deleted files

  List all deleted files ever

    git log --diff-filter=D --summary

  Search the contents of deleted files

    git log --summary -S\<string> [path/to/file] [--since=2009.1.1] [--until=2010.1.1]

  Restore a deleted file

    git checkout \<commit>~1 \<file>


## Restore a commit from the past

    git log -S"foo" -p
    git revert --no-commit \<commit>


## Drop everything since last push

    git reset --hard origin/master


## Undo your last commit, but don't throw away your changes

    git reset --soft HEAD^


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


## Make small change in last commit / I forgot to commit something

    vim file
    git add .
    git commit --amed


## I accidentally committed and pushed something to master that should have been on a _new branch_

    git branch new-branch
    git reset HEAD~ --hard
    git push origin/master --force
    git checkout new-branch
    git add .

Alternatively consider:

    git reset HEAD~ --soft
    git checkout -b new-branch
    git commit


## I accidentally committed to the wrong branch

    git reset HEAD~ --soft
    git stash
    git checkout correct-branch
    git stash pop
    git add .
    git commit -m "new commit message"


## I want to remove my last commit on remote

    git reset HEAD^
    git push -f origin develop

  If someone already fetched this commit from remote, he must remove it alos localy


## Why is my file ignored?

    git check-ignore -v path/to/file

  list all ignored files

    git ls-files -o -i --exclude-standard


## Clone all remote branches locally

    for branch in \`git branch -a | grep remotes | grep -v HEAD | grep -v master`; do
      git branch --track ${branch#remotes/origin/} $branch
    done


## Show all branches which are still not merged into master

    git branch --no-merged master


## Find the merge where your code disappeared

    git log --patch -m -G regexForMissingCode


## Shall I rebase or merge?

  People can (and probably should) rebase their _private_ trees (their own work). 
  That's a _cleanup_. But never other peoples code. That's a "destroy history"


## How can I make git ignore future revisions to a file?

  ignore:

    git update-index --skip-worktree file.txt

  allow file again:

    git update-index --no-skip-worktree file.txt

  get a list of files that are marked skipped with:

    git ls-files -v . | grep ^S


## Squash multiple commit into one commit

  Before:

        A---B---C---D---E---F

  After:

        A---B---C'          [C' = C+D+E+F]

  Method 1 "interactive rebasing":

    git rebase -i \<B>

        pick C
        squash|fixup D
        squash|fixup E
        squash|fixup F

  Method 2 "squashed merge":

    git branch temp
    git reset \<B> --hard
    git merge --squash temp
    git commit -a
    git branch -D temp

## Use a project specific git user

    git config user.name thomd
    git config user.email thomduerr@gmail.com
    git config -e
