# conda(1)

## Options

    -y                                                    # do not ask for confirmation
    -n ENV                                                # apply command to the environment ENV
    --dry-run                                             # only display what would have been done

## Manage Environment

  environment locations are in `~/.miniconda3/envs/`

    conda env list                                        # list of environments, active env is marked with *
    conda create --name NAME                              # create a new environment named NAME (default version is python 3)
    conda create --name NAME python=3.9                   # create a new environment named NAME using python 3.9
    conda env create -f environment.yml python=3.9        # create a defined environment using python 3.9
    conda create --clone NAME --name NEW_NAME             # make exact copy of an environment
    conda env remove --name NAME                          # delete an environment and everything in it

## Save and Load Environments

    conda env export | grep -v "prefix:" > my_env.yml     # save environment
    conda env create -f my_env.yml                        # create environment
    pip list --format=freeze > requirements.txt           # create pip dependencies file

## Use Environment

    conda activate NAME
    conda deactivate

    conda list                                            # installed packages
    conda list -n NAME                                    # installed packages of environment NAME
    conda list --revisions                                # history of each change to the current environment

    conda install PACKAGE=VERSION                         # install specific version of a package
    conda install --channel conda-forge PACKAGE           # install using conda-forge channel
    conda install --revision 2                            # restore environment to a previous revision
    conda install --yes --file requirements.txt           # install packages from requirements file

    conda update PACKAGE                                  # update a package into current environment

    conda env update --file environment.yml               # install dependencies of an activated env

Install packages via PIP:

    conda install pip
    export PIP\_REQUIRE\_VIRTUALENV=false
    ~/.miniconda3/envs/NAME/bin/pip install PACKAGE

