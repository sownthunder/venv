# Virtual Environments (*venv*)
ALL virtual environments used while *not* actually programming software:

To create this spec list as a file in the *current* working directory, run:

    conda list --explicit > spec-file.txt

To use the spec file to create an identical environment on the same machine or another machine:

    conda create --name myenv --file spec-file.txt

To use the spec file to install its listed packages into an existing environment:

    conda install --name myenv --file spec-file.txt

### Activating an environment

Activating environments is essential to making the software in the environments work well. Activation entails two primary functions: adding entries to PATH for the environment, and running any activation scripts that the environment may contain. These activation scripts are how packages can set arbitrary environment variables that may be necessary for their operation.

To activate an environment: 

    conda activate myenv

### Deactivating an environment

To deactivate an environment, type: 
    
    conda deactivate

Conda removes the path name for the currently active environment from your system command.

### Determining your current environment

Use the terminal or an Anaconda Prompt for the following steps.

By default, the active environment---the one you are currently using---is shown in parentheses () or brackets [] at the beginning of your command prompt:

    (myenv) $

If you do not see this, run:

    conda info --envs

In the environments list that displays, your current environment is highlighted with an asterisk (*).

By default, the command prompt is set to show the name of the active environment. To disable this option:

    conda config --set changeps1 false

To re-enable this option:

    conda config --set changeps1 true


# Sharing an environment

You may want to share your environment with someone else---for example, so they can re-create a test that you have done. To allow them to quickly reproduce your environment, with all of its packages and versions, give them a copy of your `environment.yml file`.

### Exporting the environment file

1) Activate the environment to export:  
`conda acativate myenv` 

*Replace `myenv` with the name of the environment*

2) Export your active environment to a new file:

    `conda env export > environment.yml`