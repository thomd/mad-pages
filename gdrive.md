# gdrive(1)

    gdrive about

## File Usage

    gdrive list                                             # list 30 files with query "trashed = false and 'me' in owners"
    gdrive list -q "name contains 'toon'"                   # list files with 'toon' in filename
    gdrive list -q "mimeType contains 'document'"           # list google docs
    gdrive list -q "mimeType contains 'folder'"             # list folder 
    gdrive list -q "'\<folderId>' in parents"                # list files in subdirectory
    gdrive list --order "quotaBytesUsed desc" -m 5          # list 5 largest files
    gdrive list --name-width 0                              # full width of name column
    gdrive list --absolute                                  # absolute path to file
    gdrive revision list \<fileId>                           # list revisions of a file

    gdrive info \<id>                                        # show info on file or folder
    gdrive list --no-header -m 10000 | wc -l                # count number of files & folders

    gdrive download \<fileId>                                # download file
    gdrive download query \<query>                           # download files matching a query
    gdrive revision download \<fileId> \<revisionId>          # download specific revision of a file

    gdrive mkdir \<name>                                     # create directory in root 'My Drive'
    gdrive mkdir -p \<folderId> \<name>                       # create directory within another directory
    gdrive upload -p \<folderId> \<file>                      # upload file into folder

    gdrive delete \<fileId>                                  # delete file
    gdrive delete -r \<folderId>                             # delete directory and all it's content

## Permissions

    gdrive share list \<fileId>                              # list share permissions
    gdrive share --email \<email> --type user \<fileId>       # share file with a user (sends out email)
    gdrive share --type anyone \<fileId>                     # share reader access with anyone who has the link (anyoneWithLink)
    gdrive share --discoverable \<fileId>                    # share reader access with anyone including search-engines (anyone)
    gdrive share --revoke \<fileId>                          # revoke all sharing permissions
    gdrive share revoke \<fileId> \<permissionId>             # revoke <permissionId>

## Setup Multiple Drives

  Manage multiple drives with multiple configuration folders and use

    gdrive -c ~/.gdrive-work about

  or

    export GDRIVE\_CONFIG_DIR="$HOME/.gdrive-work"
