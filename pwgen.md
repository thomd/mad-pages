
# pwgen(1)

pwgen is a Unix Password Generator

Options

    -0                # don’t include numbers
    -1                # generate one password
    -s                # hard to memorize random characters
    -y                # at least one symbol
    -B                # don’t use characters that could confuse a user when printed, such as l, 1, 0 or O
    -A                # don’t include capitals

Examples

    pwgen -1 16                    # only letters and numbers with a total of 16 characters
    pwgen -1AB                     # easy to remember password with a 8 char length
    pwgen -1AB 16
