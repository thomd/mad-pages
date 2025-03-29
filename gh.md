# gh(1)

  gh is GitHub on the command line.

    gh auth status                                # see who is logged in
    gh auth login

    gh search code foo bar                        # search code matching "foo" and "bar"
    gh search code "foo bar"                      # search code matching 'foo bar'
    gh search code foo --language python          # search code matching 'foo' in Python files
    gh search code foo --owner salesforce         # search in repos owned by an organization, e.g. 'salesforce', 'SalesforceLabs', 'developerforce' or 'forcedotcom'
    gh search code foo --repo user/repo           # search code matching 'foo' in the 'repo' repository of user 'user'
    gh search code foo --filename file.txt        # search code matching keyword 'foo' in 'file.txt' files
    gh search code foo --extension xml            # search xml files matching keyword 'foo'
    gh search code foo -w                         # open search result in browser
    gh search code --extension apex --json url,path,textMatches,repository                     # search for '*.apex' files

    gh api search/repositories -X=GET -F q='toon' -q '.items[].html_url'                       # print repo URLs containing the pattern 'toon'
    gh api search/code -X=GET -F q='filename:visidatarc' -q '.items[].html_url'                # print repo URLs having a file 'visidatarc'

    gh repo view user/repo                        # view info of repo 'user/repo'
    gh repo view user/repo -w                     # open repo 'user/repo' in browser

    gh search repos cli shell                     # search repositories matching set of keywords "cli" and "shell"
    gh search repos "vim plugin"                  # search repositories matching phrase "vim plugin"
    gh search repos --owner=microsoft             # search repositories public repos in the microsoft organization
    gh search repos --topic=unix,terminal         # search repositories with a set of topics

    gh gist list
    gh gist list -L 100                           # list 100 gists (default 10)
    gh gist list --public
    gh gist list --secret
    gh gist view ID
    gh gist view ID -f file.txt                   # view file.txt from the gist
    gh gist edit ID
    gh gist clone ID                              # clone a gist
    gh gist clone ID TARGET                       # clone a gist into a 'TARGET' folder

    gh gist create file.py -d "description"       # create gist with one file and a description
    gh gist create file.py --public               # create a public gist
    gh gist create file1.py file2.py              # create a gitst with multiple files

  Codespace

    gh repo create --add-readme --public \<name>
    gh codespace list
    gh codespace create --repo \<user>/\<name> --machine basicLinux32gb --retention-period 1h
    gh codespace view

    gh codespace ssh --codespace \`gh codespace list --json name --jq first.name`
    ...
    gh codespace stop
    gh codespace delete
