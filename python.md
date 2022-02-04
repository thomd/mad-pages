# python(1)

## pdb Debugger

insert `breakpoint()` inside a `main.py` (since Python 3.7) and run

    python main.py                                # to debug from breakpoint
    PYTHONBREAKPOINT=0 python main.py             # ignore all breakpoint calls

pdb Debugger Commands

    b(reak) \<line> [, condition]                  # set a breakpoint at a <line>
    b(reak) \<function> [, condition]              # set a breakpoint at first line of <function>
    b                                             # list all breakpoints
    c(ontinue)                                    # continue execution, only stop when a breakpoint is encountered
    n(ext)                                        # execute line (executes called functions)
    s(tep)                                        # execute line (stops inside a called function)
    r(eturn)                                      # continue execution until the current function returns
    d(own)                                        # move the current frame one level down in the stack trace
    u(p)                                          # move the current frame one level up in the stack trace
    a(rgs)                                        # print the argument list of the current function
    w                                             # show the context of the current line it is executing
    l(ist) [first[, last]]                        # list source code for the current file
    p expression                                  # evaluate and print the expression
    pp expression                                 # evaluate and pretty-print the expression
    q(uit)                                        # quit
    \<statement>                                   # Python statement (prefix with ! if statement is equal to a command)

## Virtualenv

  create virtual environment

    python -m venv .venv                          # create virtual env in `.venv`
    source venv/bin/activate                      # activate virtual env
    pip install \<package>                         # install a package
    pip install -r requirements.txt              # install packages
    ...
    deactivate

## Best Practices

  local HTTP server

    python -m http.server 80
    python -m http.server 80 -d test              # serve test folder

  local CGI server

    python -m http.server 80 --cgi                # run scripts in `./cgi-bin/`
    curl localhost/cgi-bin/test.py
