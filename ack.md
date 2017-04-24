
# ack(1)

## Search

    ack -i PATTERN                               # find PATTERN 
    ack -i PATTERN FILE                          # find PATTERN in FILE
    ack -i PATTERN FOLDER/                       # find PATTERN in all files within FOLDER
    ack -l PATTERN                               # list all files matching PATTERN and their count
    ack -g PATTERN                               # list all files matching PATTERN in file path

## Filetypes

    ack --help=types                             # list all supported filetypes
    ack --js   PATTERN                           # search for pattern in all javascript files
    ack -l --js   PATTERN                        # search for pattern in all javascript files and print filenames only
    ack -f --js                                  # list all javascript files

## Ignoring

    ack --ignore-dir=DIRNAME PATTERN             # ignore directoy
    ack --ignore-file=TYPE:ARGS PATTERN          # exclude *.cache files (ext: Extension)

FILTERS:

`is:FILENAME`: match the target filename exactly

`match:PATTERN`: match the target filename against a regular expression

`ext:EXTENSION[EXTENSION2,[,...]]`: match the extension of the target file against a list of extensions

Examples

    ack --ignore-file=match:min.js$ PATTERN      # exclude minified files
