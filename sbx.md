# Docker Sandboxes

    sbx login                                                  # authenticate
    sbx run [--name X] [--clone] AGENT [paths...]              # start an agent in a sandbox
    sbx ls                                                     # list sandboxes
    sbx exec -it NAME bash                                     # shell into a running sandbox
    sbx stop NAME                                              # stop (keeps state)
    sbx rm [--force] NAME                                      # delete
    sbx cp SRC DEST                                            # copy files in/out
    sbx ports NAME --publish H:S                               # expose a sandbox port
    
    sbx policy ls
    sbx policy log
    sbx policy allow network URL_PATTERN                       # manage network access

    sbx diagnose                                               # troubleshoot

