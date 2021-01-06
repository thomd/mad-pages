# pip(1)

Usage

    python -m venv venv                                  # create virtual env
    source venv/bin/activate                             # activate virtual env
    pip install PACKAGE                                  # install a package
    pip install PACKAGE==VERSION                         # install version VERSION of package PACKAGE
    pip install PACKAGE==                                # show installable versions of package PACKAGE

Check version

    python -c "import flask; print(flask.\_\_version__)"

List lookup paths

    python -c "import sys; print(sys.path)"

Create a Dependencies File

    pip freeze > requirements.txt                        # output installed packages in requirements format
    pip install -r requirements.txt                      # activate a virtualenv and install packages
