# Go

## Go PATH

    cd go-project
    sgn                                                  # set GO Path-based environment in current directory

## Go Modules

    cd go-project                                        # ourside $GOPATH !
    go mod init github.com/thomd/temp

    go list -m -versions github.com/gookit/color         # list available tagged versions
    go get github.com/gookit/color@v1.3.1

    go list -m all                                       # list all modules

# go(1)

## go run

    go run main.go                                       # run executable code
    go run .                                             # run file containg main()

## go build

    go build                                             # build static binary of file containg main() and name it like folder
    go build -o \<name>                                   # build static binary with name <name>
    GOOS=linux go build                                  # build static binary for linux platform

## go install

    go install                                           # perform a go build and move executable to $GOBIN

## go get

    go get ./...                                         # install all dependencies. The pattern ... tells to go down recursively
    go get github.com/thomd/package                      # download and install packages $GOPATH/src
    go get -u github.com/thomd/package                   # update packages to $GOPATH/src
    go get github.com/thomd/package@v1.2.3               # download specific version
    go get github.com/thomd/package@master               # download head of specific branch
    go get github.com/thomd/package@3702bed2             # download specific revision

# Go Testing

    go test                                              # test any files matching <code>*_test.go</code>
    go test ./...                                        # test entire <code>pkg</code>
    go test -v                                           # be verbose
    gotestsum --watch

# Go Debugging

Usage

    dlv debug main.go                        # start debugging
    dlv test .                               # start debugging tests

    > help | h                               # show help
    > break | b \<file>:\<line>                # set breakpoint at line \<line> in file \<file>, e.g. `app.go:12`
    > break | b \<pkg>.\<func>                 # set breakpoint at \<func> function of \<pkg> package, e.g. `main.main`
    > breakpoints | bp                       # list breakpoints
    > cond \<bp> \<boolean-expression>         # conditional breakpoint
    > continue | c                           # run until breakpoint
    > next | n                               # step over to next line
    > list | l                               # show source code
    > step | s                               # step into function
    > stepout | so                           # step out from function

    > funcs main                             # print functions in main package
    > types main                             # print types in main package

    > whatis foo                             # print type of variable foo
    > print foo | p foo                      # print value of variable foo

    > vars                                   # package variables
    > locals                                 # local variables
    > args                                   # function arguments

  Example Debug Session

    dlv debug main.go
    > b main.main
    > c
    > n
    > p myVar
