
# bash(1)

## Debugging

  enable debugging with option `-v` (show current script line) or `-x` (enable debug-modus):

    set -vx                                            # enable debugging
    set +vx                                            # disable debugging
    sh -v script.sh                                    # run script verbosely
    sh -x script.sh                                    # run script with debug info
    sh -vx script.sh 2>&1 | tee logfile.log            # run script with debug info and log


## Redirection

file descriptors `fd`:

  stdin: **0**
  stdout: **1**
  stderr: **2**

  **1** and **2** goes to the terminal

    (echo >&2 "error"; echo "message")                      # "error" "message"
    (echo >&2 "error"; echo "message") >/dev/null           # "error"
    (echo >&2 "error"; echo "message") 2>/dev/null          # "message"
    (echo >&2 "error"; echo "message") >/dev/null 2>&1      # ""
