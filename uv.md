# uv(1)

## Existing Modern Project

    git clone ...
    uv sync                                      # given pyproject.toml & uv.lock, create .venv and install packages
    uv run main.py

## Existing Legacy Project

    git clone ...
    uv venv                                      # create virtual environment with global Python
    uv pip install -r requirements.txt           # install from a requirements.txt file
    uv run main.py

## Project Development

    uv init my_project
    uv add PACKAGE                               # add package to pyproject.toml & uv.lock and install into .venv
    uv run main.py

## Quick Tryouts

    uv venv
    uv pip install PACKAGE
    uv run main.py

## Tools

    uv tool install PACKAGE                                   # globally install executable PACKAGE into `~/.local/bin`
    uv tool dir                                               # where is it installed to?
    uv tool list                                              # list installed packages
