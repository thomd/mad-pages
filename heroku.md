
# heroku(1)

Heroku is a cloud application platform

## Quickstart

    heroku login
    heroku create
    git push heroku master
    heroku open

Heroku CLI automatically detects the *app name* by scanning the *git remotes* for the current working copy.

## Commands

    heroku login                              # login with email and password. Generates an API token in ~/.netrc

    heroku apps                               # list all apps on heroku
    heroku apps:create NAME                   # create NAME app [Alias: heroku create NAME]
    heroku apps:create --region eu NAME       # create NAME app in the EU region
    heroku apps:destroy -a NAME               # destroy NAME app
    heroku apps:info -a NAME                  # show detailed information
    heroku apps:open -a NAME                  # open in web browser

    heroku logs -t                            # stream logs

    heroku config                             # print config vars
    heroku config:set KEY=VALUE               # set config var
    heroku config:unset KEY                   # unset config var

    heroku git:clone -a APP                   # clone an app
    heroku git:remote -a APP                  # adds an heroku remote to an app

    heroku status                             # show current status
    heroku releases                           # show current releases
    heroku releases:rollback v102             # rollback to version v102

    heroku run bash                           # run bash locally

## Teams

    heroku teams                              # list teams I belong to
    heroku members -t \<team>                  # list members of a team
