# Network Automation Utilities

This package contains a variety of modules. Some are for general Python tasks like file conversions, others are for aiding Network Engineering  Automation. I have and still use many of these utilities as an Automation Engineer. 

Offical documentation can be found [here](https://ADD-NEW-LINK).

## Installation



`poetry add cwe_tools`.

If you can *not* install, clone the repository & run `poetry install` to install the package. 

_NOTE:_ Other package managers such as `pip` can also be used for installation.

You can also clone and install the package locally with:

```bash
$ git clone (https://ADD-NEW-LINK)
$ cd cwe_tools
$ poetry install  # Use --no-dev if you don't want development dependencies
```

## Quick Start

Example of using a utility in the `data_converter` module to convert a Python object to a YAML file:

See source code for more info on the utilities and their associated parameters.

```python
# Import module
>>> 
>>> from netauto_utils import data_converter
>>> 
>>> python_obj = {
...     "Yaml Data": [
...         {"a": 1, "b": 2},
...         {"c": 3, "d": 4},
...         {"e": 5, "f": 6},
...     ]
... }
>>> 
>>> write_file = True
>>> 
>>> filename = 'my_new_yaml_file.yml'
>>> 
>>> 
>>> print(data_converter.python_to_yaml(python_obj, write_file, filename))
my_new_yaml_file.yml has been created! 👍

Yaml Data:
  - a: 1
    b: 2
  - c: 3
    d: 4
  - e: 5
    f: 6

>>>
```
The new YAML file generated `my_new_yaml_file.yml`.
```
---
Yaml Data:
  - a: 1
    b: 2
  - c: 3
    d: 4
  - e: 5
    f: 6

```
## Cutting a New Release
1. Checkout develop branch - ensure you have the latest commits by running git pull
2. Create new branch - git checkout -b <new-branch>

Perform the following operations:
- Run poetry version <major/minor/patch> to update version in pyproject.toml
- Edit CHANGELOG.md - Update for new version with changes included in new version
- Run poetry update to update Python dependencies
- Commit all changes - push branch to GitLab
- Open new MR for your new branch into master
- After the merge is completed, cut a new tag (Repository > Tags > Name: vX.X.X)
- Open new MR from master into develop to sync branches (master will not be deleted).

