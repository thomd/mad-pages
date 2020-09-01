
# go(1)

## go env

    go env
    go help environment
    go env GOPATH                                   # print GOPATH
    sgo                                             # set GO environment inn current directory

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

    dlv debug main.go                # start debugging

    > help | h                       # show help
    > break | b app.go:12            # set breakpoint at line 12 of app.go
    > break | b \<pkg>.\<func>         # set breakpoint at \<func> function of \<pkg> package
    > break | b main.main            # set breakpoint at main function of main package
    > breakpoints | bp               # list breakpoints
    > continue | c                   # run until breakpoint
    > next | n                       # step over to next line
    > list | l                       # show source code

    > funcs main                     # print functions in main package
    > types main                     # print types in main package

    > whatis foo                     # print type of variable foo
    > print foo | p foo              # print value of variable foo

    > vars                           # package variables
    > locals                         # local variables
    > args                           # function arguments

  Example Debug Session

    dlv debug main.go
    > b main.main
    > c
    > n
    > p myVar


# Go Specification

## Go Pointer

A pointer is a variable that stores the memory address of another variable.

Go does not support Pointer Arithmetic. You can't add to or subtract from pointers.


    & operator                # get memory address
    \* operator                # access the value stored at an address. This is called dereferencing or indirecting
    \*T                        # pointer type. Here, the \* is not an operator, it is part of a type, hence \*T and T are different types.

  Example

    var age int = 49
    var ptr *int = &age
    var ptr = &age            # type inference
    var value = *ptr          # 49
    *ptr = 50                 # Change value stored in the pointed variable through the pointer

  Create a pointer using the built-in new() function:

    ptr := new(int)           # create pointer to an int type
    *ptr = 100
    fmt.Print(*ptr)           # 100
