
# What files are in my repository?

    git ls-tree HEAD -r --name-only

# Find largest file in my repository

    git ls-tree HEAD -l -r | sort -k 4 | tail -1

# How to remove a just committed file/folder

    git ls-tree -r --name-only HEAD
    git rm \<FILE>
    git rm -r \<FOLDER>
    git commit --amend

# Restore a deleted file

    git log -- path/to/filename
    git revert \<SHA1>

# Restore a change from the past

    git log -S"foo" -p
    git revert -n \<SHA1>
