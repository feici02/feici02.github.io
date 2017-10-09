---
layout: post
title:  "Pipenv Cheatsheet"
tags: python
---

Pipenv is the officially recommended Python packaging tool. Here is its usage:

```
# install
$ pip install pipenv

$ mkdir pipenv-test
$ cd pipenv-test

# Create a new project using Python 3
$ pipenv --three

# Output virtualenv information
$ pipenv --venv

# activate venv
$ pipenv shell

# check Python interpreter
$ which python
# or
$ pipenv --py

# install packages
$ pipenv install requests
# install a dev dependency
$ pipenv install --dev pytest 

# show dependency graph
$ pipenv graph

# delete Pipfile.lock for test
$ rm -f Pipfile.lock
# generate lock file again
$ pipenv lock

# uninstall everything
$ pipenv uninstall --all

# all gone
$ pipenv graph

# install all denpendencies, including the dev
# if following command is run without a venv,
# a venv will be created automatically.
$ pipenv install --dev

# exit from venv
$ exit
# remove venv
$ pipenv --rm
```

## Reference
1. <https://docs.pipenv.org/>
1. <https://github.com/kennethreitz/pipenv>
