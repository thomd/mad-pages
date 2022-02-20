# conda(1)

If conda(1) does not work as expected, check `~/.bash_profile` for conda related lines.

    conda info                                      # print global info
    conda config --describe                         # list all available config parameters

## Manage Environment

  environment locations are in `~/.miniconda3/envs/`

    conda env list                                  # list of environments, active env is marked with *
    conda create --name NAME                        # create a new environment named NAME (default version is python 3)
    conda create --name NAME python=3.7             # create a new environment named NAME using python 3.7
    conda create --clone NAME --name NEW_NAME       # make exact copy of an environment
    conda env remove --name NAME                    # delete an environment and everything in it

## Save and Load Environments

    conda env export > environment.yaml             # save environment to a yaml file
    conda env create --file environment.yaml        # create environment from a text file
    pip list --format=freeze > requirements.txt     # create pip dependencies file

## Use Environment

    conda activate NAME
    conda deactivate

    conda list                                      # installed packages
    conda list --revisions                          # history of each change to the current environment

    conda install PACKAGE                           # install a package into current env
    conda install --channel conda-forge PACKAGE     # install using conda-forge channel
    conda install --revision 2                      # restore environment to a previous revision
    conda install --yes --file requirements.txt     # install packages from requirements file

    conda update PACKAGE                            # update a package into current environment
    conda update --all                              # update all package in an environment

Install packages via PIP:

    conda install pip
    PIP_REQUIRE_VIRTUALENV=false ~/.miniconda3/envs/<name>/bin/pip install PACKAGE
