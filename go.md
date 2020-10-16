# go(1)

## New Go project

Using $GOPATH

    cd go-project
    sgn                                             # set GO Path-based environment in current directory

Using Go Modules

A module is a collection of related Go packages that are versioned together as a single unit:

* a Repository contains one or more Go Modules.
* each Module contains one or more Go Packages.
* each Package consists of one or more Go source files in a single directory.

    cd go-project                                   # ourside $GOPATH !
    go mod init github.com/thomd/go-project


## go env

    go env
    go help environment
    go env GOPATH                                   # print GOPATH

## go run

    go run main.go                                  # run executable code
    go run .                                        # run file containg main()

## go build

    go build                                        # build static binary of file containg main() and name it like folder
    go build -o \<name>                              # build static binary with name <name>
    GOOS=linux go build                             # build static binary for linux platform

## go get

    go get ./...                                    # install all dependencies. The pattern ... tells to go down recursively
    go get github.com/thomd/package                 # download and install packages $GOPATH/src
    go get -u github.com/thomd/package              # update packages to $GOPATH/src
    go get github.com/thomd/package@v1.2.3          # download specific version
    go get github.com/thomd/package@master          # download head of specific branch
    go get github.com/thomd/package@3702bed2        # download specific revision

# Go Debugging

Install

    xcode-select --install
    go get -u github.com/go-delve/delve/cmd/dlv

Usage

    dlv debug main.go                     # start debugging

    > help | h                            # show help
    > break | b app.go:12                 # set breakpoint at line 12 of app.go
    > break | b \<pkg>.\<func>              # set breakpoint at \<func> function of \<pkg> package
    > break | b main.main                 # set breakpoint at main function of main package
    > breakpoints | bp                    # list breakpoints
    > cond \<bp> \<boolean-expression>    # conditional breakpoint
    > continue | c                        # run until breakpoint
    > next | n                            # step over to next line
    > list | l                            # show source code
    > step | s                            # step into function
    > stepout | so                        # step out from function

    > funcs main                          # print functions in main package
    > types main                          # print types in main package

    > whatis foo                          # print type of variable foo
    > print foo | p foo                   # print value of variable foo

    > vars                                # package variables
    > locals                              # local variables
    > args                                # function arguments

  Example Debug Session

    dlv debug main.go
    > b main.main
    > c
    > n
    > p myVar
