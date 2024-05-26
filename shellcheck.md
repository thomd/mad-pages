# shellcheck(1)

    shellcheck script.sh                                   # lint
    shellcheck -e SC2059 script.sh                         # disable a specific rule
    shellcheck -f gcc script.sh | wc -l                    # count errors
    shellcheck --color=always script.sh | less -r          # preserve colors when piping to less

Disable Shellcheck Rules
add at top of file to disable rules in a file:

#!/usr/bin/env bash
# shellcheck disable=SC2003,SC2219

add at a specific line to disable line:

hexToAscii() {
  # shellcheck disable=SC2059
  printf "\x$1"
}

