# pipx(1)

Python binaries are located in `~/.local/bin/PACKAGE` and symlinked to `~/.local/pipx/venvs/PACKAGE/bin/PACKAGE`

    pipx install PACKAGE
    pipx list

# Run Single-Use Python Apps

    pipx run ruff check .                              # run Python ruff linter on files in current directory
    cat file.md | pipx run rich-cli -m -               # format markdown output using the rich library

# Use a Specific Python Version

    pyenv shell VERSION                                # set version to be used in the current shell
    pyenv which python                                 # get path /path/to/python to current version
    pipx install --python=/path/to/python PACKAGE      # install PACKAGE with python VERSION

