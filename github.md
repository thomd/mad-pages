# GitHub Code Search

    language:\<lang>                    # search for code based on what language it's written in
    filename:\<name>                    # match code files with a certain filename
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


# gh(1)

gh is GitHub on the command line.

    gh auth status                                # see who is logged in
    gh auth login

    gh repo create my-project                     # create new repo user/my-project
    gh repo create                                # create new repo based on name of CWD

    gh gist list
    gh gist list -L 100                           # list 100 gists (default 10)
    gh gist list --public
    gh gist list --secret
    gh gist view ID
    gh gist edit ID
    gh gist clone ID                              # clone a gist
    gh gist clone ID TARGET                       # clone a gist into a 'TARGET' folder
    
    gh gist create file.py -d "description"       # create gist with one file and a description
    gh gist create file.py --public               # create a public gist
    gh gist create file1.py file2.py              # create a gitst with multiple files


# act(1)

Run GitHub Actions locally

    act -l                                        # list actions
    act                                           # run the default push event
    act pull_request                              # run a specific event
    act -j test                                   # run a specific job
    act -n                                        # run in dry-run mode
    act -v                                        # enable verbose-logging

# Personal Access Token (PAT)

Clone repositories protected by SAML SSO using a PAT:

    git clone https://\<user>:\<pat>@github.com/orga/repo.git

