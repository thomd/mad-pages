# GitHub Code Search

    language:\<lang>                    # search for code based on what language it's written in
    path:**/\<file>                     # match code files with a certain filename
    owner:\<name>                       # search in repos of \<name> only
    extension:\<ext>                    # match code files with a certain file extension

    in:path                             # matches code where search term appears in the file path
    in:file                             # matches code where search term appears in the file content
    in:name                             # matches repositories with the search term in their name
    in:description                      # matches repositories with the search term in their description
    in:readme                           # matches repositories with the search term in their README file

    NOT                                 # exclude Operator: Matches repositories that have a word but not another word
    -                                   # exclude Qualifier: Matches repositories that have a word but not in an entity

  Examples

    sfcc language:go
    sfcc fileame:package.json
    sfcc extension:json
    foo NOT bar
    foo -language:css
    sfcc in:name
    sfcc in:name,description,readme
    Makefile owner:thomd

# Github Personal Access Token (PAT)

  Clone repositories protected by SAML SSO using a PAT:

    git clone https://\<user>:\<pat>@github.com/orga/repo.git

# act(1)

Run GitHub Actions locally

    act -l                                        # list actions
    act                                           # run the default push event
    act pull_request                              # run a specific event
    act -j test                                   # run a specific job
    act -n                                        # run in dry-run mode
    act -v                                        # enable verbose-logging

