# surge(1)

Usage

    surge login                                     # authentication (see ~/.netrc)
    surge list                                      # list all domains
    surge teardown                                  # remove a surge (will be asked for name)
    surge                                           # deploy to http://*.surge.sh
    surge -d foo.surge.sh                           # deploy to http://foo.surge.sh
    echo foo.surge.sh > CNAME && surge              # deploy to http://foo.surge.sh
