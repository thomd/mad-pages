# pip(1)

Usage

    python -m venv venv                                  # create virtual env
    source venv/bin/activate                             # activate virtual env
    pip install PACKAGE                                  # install a package
    pip install PACKAGE==VERSION                         # install version VERSION of package PACKAGE
    pip install PACKAGE==                                # show installable versions of package PACKAGE
    pip install -r requirements.txt                      # install packages
    pip install --upgrade PACKAGE                        # update package

    PIP\_REQUIRE\_VIRTUALENV=false pip install PACKAGE     # install without required virtualenv; or use `gpip`

List Installed Packages

    pip list
    pip list -o                                          # list outdated packages
    pip show PACKAGE                                     # show information about a package
    pip freeze > requirements.txt                        # output installed packages in requirements format

Check Version of a Package

    python -c "import flask; print(flask.\_\_version__)"

List Lookup Paths of Packages

    python -c "import sys; print(sys.path)"

Create a Dependencies File

    pip freeze > requirements.txt                        # output installed packages in requirements format
