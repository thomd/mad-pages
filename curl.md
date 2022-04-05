
# curl(1)

## Verbose

    curl -v
    curl --trace-ascii \<file>
    curl --trace \<file>

  use `-` as filename to have the output sent to `stdout`

## Output

  Write output to a local file named like the remote file

    curl -O

  Write output to a file

    curl -o \<file>
    curl http://{site,host}.host[1-5].com -o "#1_#2"

## POST

    -d "string"
    -d @file                       # post content of 'file'

  Multipart Formpost

    curl -F name=value
    curl -F name=@file

## PUT

    curl -T \<file>

  Automatically find out where to resume a transfer

    curl -C -

## Cookies

    curl -b "c=1; d=2"

  Read Cookiejar

    curl -b \<file>

  Write Cookiejar

    curl -c \<file>

## Headers

  Add header

    curl -H "name: value"

  Remove header

    -H "name:"

## Formatting

    curl -s httpbin.org/headers | jq '.'
    curl -s httpbin.org/xml | xmllint --format -
    curl -s httpbin.org/xml | xmllint --format - | highlight -S xml -O xterm256 -s neon

