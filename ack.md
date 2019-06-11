
# ack(1)

## Search

    ack -i PATTERN                               # find PATTERN
    ack -i PATTERN file                          # find PATTERN in a given file
    ack -i PATTERN folder/                       # find PATTERN in all files within a given folder
    ack -l PATTERN                               # print files matching PATTERN and their count
    ack -g PATTERN                               # print files matching PATTERN in file path (same as: ack -f | ack -C0 json)

## Filetypes

    ack --help=types                             # list all supported filetypes
    ack --js PATTERN                             # search for pattern in all javascript files
    ack -l --js PATTERN                          # search for pattern in all javascript files and print filenames only
    ack -f                                       # list all files
    ack -f --js                                  # list all javascript files
    ack --ts --notsdef PATTERN                   # search in all typescript files but not in definitions

## Ignoring

    ack --ignore-dir=DIRNAME PATTERN             # ignore directoy
    ack --ignore-file=TYPE:ARGS PATTERN          # exclude *.cache files (ext: Extension)

FILTERS:

`is:FILENAME`: match the target filename exactly

`match:PATTERN`: match the target filename against a regular expression

`ext:EXTENSION[EXTENSION2,[,...]]`: match the extension of the target file against a list of extensions

Examples

    ack --ignore-file=match:min.js$ PATTERN      # exclude minified files

## Best Practices

    ack --js -w const                            # search for the keyword const in all javascript files
    ack -B 10 -A 5 PATTERN                       # display 10 lines before amd 5 line after
