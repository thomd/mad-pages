
# curl(1)

## Verbose

    curl -v
    curl --trace-ascii \<file>
    curl --trace \<file>

  use `-` as filename to have the output sent to `stdout`

## Write output

    curl -O
    curl -o \<file>

## POST

    -d "string"
    -d @file

  multipart formpost

    curl -F name=value
    curl -F name=@file

## PUT

    curl -T \<file>

  automatically find out where to resume a transfer

    curl -C -

## Cookies

    curl -b "c=1; d=2"

  read cookiejar

    curl -b \<file>

  write cookiejar

    curl -c \<file>

## Headers

  add header

    curl -H "name: value"

  remove header

    -H "name:"

