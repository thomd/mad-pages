# GitHub Code Search

    language:                 # search for code based on what language it's written in
    filename:                 # match code files with a certain filename
    extension:                # match code files with a certain file extension
    in:path                   # matches code where search term appears in the file path
    in:file                   # matches code where search term appears in the file content
    NOT                       # exclude Operator: Matches repositories that have a word but not another word
    -                         # exclude Qualifier: Matches repositories that have a word but not in an entity

  Examples

    sfcc language:go
    sfcc fileame:package.json
    sfcc extension:jsonn
    foo NOT bar
    foo -language:css	

# act(1)

Run GitHub Actions locally

    act -l                    # list actions
    act                       # run the default push event
    act pull_request          # run a specific event
    act -j test               # run a specific job
    act -n                    # run in dry-run mode
    act -v                    # enable verbose-logging
