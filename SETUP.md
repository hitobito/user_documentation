# Setup the sphinx / RtD environment

This document outlines the setup of the sphinx and transifex client for
building and translating the `user_documentation`.

Currently only Linux in general and Ubuntu in particular are covered.
More to come, watch this space.

## Linux

### Via Python `virtualenv`

Install python virtualenv

```bash
$ sudo apt install virtualenv # on Ubuntu
```

Create a virtualenv and install the sphinx dependencies

```bash
$ cd workdir
$ virtualenv sphinx
$ sphinx/bin/pip install sphinx sphinx-intl[transifex] sphinx_rtd_theme
```

Set the path to the virtualenv bin directory

```bash
export PATH=$(pwd)/sphinx/bin:${PATH}
```
