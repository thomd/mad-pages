# bash(1)

## Debugging

  enable debugging with option `-v` (show current script line) or `-x` (enable debug-modus):

    set -vx                                            # enable debugging
    set +vx                                            # disable debugging
    sh -v script.sh                                    # run script verbosely
    sh -x script.sh                                    # run script with debug info
    sh -vx script.sh 2>&1 | tee logfile.log            # run script with debug info and log
