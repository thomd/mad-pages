# uv(1)

## Virtual Environment

    uv venv                                                   # create virtual environment with global Python
    uv pip install PACKAGE                                    # install a package in the new virtual environment
    uv pip install -r requirements.txt                        # install from a requirements.txt file

## Usage

    uv venv --seed
    uv pip install PACKAGE
    uv run main.py

## Tools

    uv tool install PACKAGE                                   # install a executable binary PACKAGE globally into `~/.local/bin`
    uv tool dir                                               # where was it installed to?
    uv tool list                                              # list installed packages
