# diff(1)

    diff -rq folder1 folder2                   # compare folders
    diff -rq -x ".git" folder1 folder2         # compare folders, but exclude .git
    cmp -cl binary1 binary2                    # compare binary files
    diff -y <(ls -l dir1) <(ls -l dir2)        # compare result of two streams
