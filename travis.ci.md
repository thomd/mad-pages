
# travis(1)

Travis command line client

    sudo gem install travis

## Usage

    travis login                 # login
    travis whoami                # current user

    travis status                # checks status of the latest build
    travis show                  # show build
    travis history               # displays a projects build history
    travis logs                  # stream test logs

## .travis.yml

Travis Build Environment

    travis init                  # create a .travis.yml file
    vim .travis.yml              # see Configure build
    travis lint                  # lint
    travis enable                # enable the project
