# shellcheck(1)

    shellcheck script.sh                                   # lint
    shellcheck -e SC2059 script.sh                         # disable a specific rule
    shellcheck -f gcc script.sh | wc -l                    # count errors
    shellcheck --color=always script.sh | less -r          # preserve colors when piping to less

Shellcheck Rules: https://www.shellcheck.net/wiki/

## Disable Rules in a File

    #!/usr/bin/env bash
    # shellcheck disable=SC2003,SC2219

## Disable Rule for a Specific Line

    hexToAscii() {
        # shellcheck disable=SC2059
        printf "\x$1"
    }

