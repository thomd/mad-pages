# node(1)

## Debugging

    node inspect script.js                   # enable debugging (add debugger statements in code)
    node inspect -p \<pid>                    # connect to a running process via the pid

  Commands

    > list(5)                                # List scripts source code with 5 line context

    > cont, c                                # Continue execution
    > next, n                                # Step next
    > step, s                                # Step in
    > out, o                                 # Step out

    > repl                                   # evaluate code remotely (leave with CTRL-C)
    > backtrace, bt                          # print backtrace of current execution frame (call stack)

    > watch('my_expression')
    > watchers                               # Print active watchers
    > unwatch('my_expression')
    > exec 'my_expression'                   # Execute an expression in debugging script's context

    > sb(123)                                # set breakpoint in line 123 of current script
    > sb('script.js', 123)                   # set breakpoint in line 123 of script.js (must be loaded)

    > restart                                # Restart script
    > backtrace, bt                          # Print backtrace of current execution frame
