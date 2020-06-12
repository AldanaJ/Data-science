# Python Binder

This repo builds on the [r binder](https://github.com/binder-examples/r) and [jupyter lab binder](https://github.com/binder-examples/jupyterlab) and is complementary to the [multi-language-demo binder](https://github.com/binder-examples/multi-language-demo) with examples on using both R and python in both Jupyter Lab and RStudio.

 - Launch in Jupyter Lab: [![Binder](http://mybinder.org/badge.svg)](https://mybinder.org/v2/gh/AldanaJ/Data-science/master)

## Binder Setup

Modify the files in the `binder` sub-directory to specify required dependencies for R and python. Binder will generate a docker image for your repository after every change to the repo and then will re-use the docker image on subsequent launches. This means that the first time you launch binder for the latest version of your branch, it may take some time to launch (especially with a lot of R dependencies which are all compiled from source) but will be fast for everyone else afterwards. Switching between `RStudio` vs. `Jupyter Lab` as the IDE is accomplished easily by changing the binder link as described below - the required dependencies for both are automatically installed and do not need to be explicitly listed in the respective configuration files.

**Important**: binder will *only* work for public repositories. If your repository is private, you will have to make it public in the repository settings before you can launch it in binder.

### Python

 - modify the `binder/environment.yml` file to specify the dependencies. The file is a standard [conda environment config file](https://conda.io/docs/user-guide/tasks/manage-environments.html#create-env-file-manually) and thus supports conda packages, version definitions, multiple source channels as well as pip installations.
 - modify the `binder/postBuild` file for any JupyterLab extensions or other direct install commands

## Binder Link

### Jupyter Lab

 - modify the following link to launch your repo in an RStudio binder (`USER`, `REPO`, `BRANCH`): `http://mybinder.org/v2/gh/USER/REPO/BRANCH?urlpath=lab`
 - modify the following markdown code to create a launch badge like the one at the top this README: `[![Binder](http://mybinder.org/badge.svg)](http://mybinder.org/v2/gh/USER/REPO/BRANCH?urlpath=lab)`
