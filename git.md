
# Git Best Practices

## What have I done in my branch?

    git log develop..
    git diff develop...


## What have others done since I branched

    git log ..develop
    git diff ...develop


## What's behind or ahead origin/develop?

    git fetch --all

  behind:

    git log ..origin/develop
    git diff ...origin/develop

  ahead:

    git log origin/develop..
    git diff origin/develop...


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


## Show change history of a file

    git log --follow -p -- \<file>

  or

    tig \<file>


## Find and restore deleted files

  List all deleted files ever

    git log --diff-filter=D --summary

  Search the contents of deleted files

    git log --summary -S\<string> [path/to/file] [--since=2009.1.1] [--until=2010.1.1]

  Restore a deleted file

    git checkout \<commit>~1 \<file>


## Un-Commit a file

    git reset @~ <file> && git commit --amend --no-edit


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


## Ignoring Version-Controlled Files

    cat file-to-ignore >> .gitignoe
    git rm --cached file-to-ignore

    cat dir-to-ignore >> .gitignoe
    git rm -r --cached dir-to-ignore


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


## delete a tag on remote

  delete a tag named \<tag>

    git tag -d \<tag>
    
  remove tag \<tag> from remote repo

    git push origin :refs/tags/\<tag>

## create hotfix branch based on tag

    git checkout -b hotfix/\<tag> \<tag>
