Conda Buildpack
===============

This is a [Heroku Buildpack](https://devcenter.heroku.com/articles/buildpacks) for [Conda](http://conda.pydata.org/),
the Python distribution for scientific computing by Continuum Analytics. It is based on the lightweight Miniconda
distribution, keeping the final slug size as small as possible.

To control the packages installed by conda, supply a `requirements-conda.txt` file (which can be created by
capturing the output of `conda list -e` for your working conda environment).

All other packages can then be installed with a `requirements-pip.txt` file for [pip](https://github.com/pypa/pip)
to process.  In this way, you can install binary packages via Miniconda for everything you can and
still use pip for anything you can't.

Note for Mac Developers
-----------------------
If you're on a Mac and want to test the scripts locally like I did, you'll need to make your local
environment as close as possible to a GNU Linux distribution using [Homebrew](https://brew.sh/) with the following
commands:

1) Fix issues with "date":
brew install coreutils
Update your path with PATH="/usr/local/opt/coreutils/libexec/gnubin:$PATH"

2) Fix issues with "sed":
brew install gnu-sed --with-default-names

3) Fix issues with "find":
brew install findutils --with-default-names
