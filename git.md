# Git Best Practices

Show changes of a specific commit

    git log A^..A -p

# Resolve Merge Conflict

    git merge --abort                 # OPTION 1: abort the merge and get back to the state before `git merge develop`
    vim \<file>                        # OPTION 2: manually resolve conflicts in the file
    git checkout --theirs \<file>      # OPTION 3: accept remote version
    git checkout --ours \<file>        # OPTION 4: use local version
    git add \<file>
    git merge --continue              # checks whether there is a (interrupted) merge in progress before calling `git commit`


# Show change history of a file

    git log --follow -p -- \<file>
    tig \<file>                        # alternatively use `tig`


# Find and restore deleted files

  List all deleted files ever

    git log --diff-filter=D --summary

  Search the contents of deleted files

    git log --summary -S\<string> [path/to/file] [--since=2009.1.1] [--until=2010.1.1]

  Restore a deleted file

    git checkout \<commit>~1 \<file>


# Restore a commit from the past

    git log -S"foo" -p
    git revert --no-commit \<commit>


# Undo your last commit, but don't throw away your changes

    git reset --soft HEAD^


# Uncommit a file

    git reset @~ <file> && git commit --amend --no-edit


# Restore old state of a specific file

    git log
    git checkout \<sha1> -- path/to/file


# Make small change in last commit / I forgot to commit something

    vim file
    git add .
    git commit --amend


# I accidentally committed and pushed to master that should have been on a new branch

    git branch new-branch
    git reset HEAD~ --hard
    git push origin/master --force
    git checkout new-branch
    git add .

  Alternatively consider:

    git reset HEAD~ --soft
    git checkout -b new-branch
    git commit


# I accidentally committed to the wrong branch

    git reset HEAD~ --soft
    git stash
    git checkout correct-branch
    git stash pop
    git add .
    git commit -m "new commit message"


# Why is my file ignored?

    git check-ignore -v path/to/file

  list all ignored files

    git ls-files -o -i --exclude-standard


# Find the merge where your code disappeared

    git log --patch -m -G regexForMissingCode


# Empty Commit

    git commit --allow-empty -m "jenkins trigger" && git push


# Stashing Changes

    git stash
    git stash -p                        # interactively specify changes included in this stash
    git stash -u                        # include also untracked files
    git stash -k                        # stash only unstaged changes (--keep-index)
    git stash push -- file.txt          # stash only a specific file

    git stash list                      # list all stashes; alias git s
    git stash show                      # show files of first stash
    git stash show stash@{1}            # show files of a specific stash

    git stash pop stash@{1}             # apply a stash and drop from stack
    git stash pop                       # apply first stash and drop from stack

    git stash drop                      # drop latest stash
    git stash drop stash@{1}            # drop a stash
    git stash clear                     # clear all stashes


# Find Branch which Contains a Specific File

    git log --all -- '**/file.txt'
    git branch -a --contains \<sha>


# Find largest file in my repository

    git ls-tree HEAD -l -r | sort -n -k4 | tail -1

