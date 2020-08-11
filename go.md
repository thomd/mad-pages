
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

# Go Debugginng

Install

    xcode-select --install
    go get -u github.com/go-delve/delve/cmd/dlv

Usage

    dlv debug main.go                # start debugging
    > break app.go:12                # set breakpoint at line 12 of app.go
    > break main.main                # set breakpoint at main function of main package
    > breakpoints                    # list breakpoints
    > continue | c                   # run until breakpoint
    > print foo | p foo              # print variable foo
    > funcs main                     # print functions in main package
    > types main                     # print types in main package
    > next | n                       # step over to next line
    > list | l                       # show source code

    > vars                           # package variables
    > locals                         # local variables
    > args                           # function arguments
