# surge(1)

Upload

    surge login                                     # authentication (see ~/.netrc)
    surge list                                      # list all domains
    surge teardown                                  # remove a surge (will be asked for name)
    surge                                           # deploy to https://*.surge.sh
    surge -d foo.surge.sh                           # deploy to https://foo.surge.sh
    echo foo.surge.sh > CNAME && surge              # deploy to https://foo.surge.sh

Download

    curl foo.surge.sh/auto.appcache
    surge-dl foo                                    # download files from https://foo.surge.sh into the current directory
