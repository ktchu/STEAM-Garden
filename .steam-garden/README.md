README - STEAM Garden Setup
==============================================================================

------------------------------------------------------------------------------

Table of Contents
-----------------

1. [Setup Files][#1]

2. [Setting Up the Repository][#2]

------------------------------------------------------------------------------

## 1. Setup Files

```
├── pyproject.toml      <- configuration file for STEAM Garden tools
|                          (e.g., black, pre-commit, flake8)
└── .steam-garden
    ├── README.md       <- README for STEAM Garden set up
    └── dot-envrc       <- direnv configuration file for STEAM Garden
```

------------------------------------------------------------------------------

## 2. Setting Up the Repository

* ___Prerequisites___

  * Install Python 3.9 (or a later version).

  * Install [Poetry](https://python-poetry.org/).

* Set up the repository to use `direnv` to manage the environment.

  * ___Prerequisite___. Install `direnv`.

  * Copy `.steam-garden/dot-envrc` to the repository root directory, and
    rename it to `.envrc`.

    ```shell
    $ cd $REPOSITORY_ROOT_DIR
    $ cp .steam-garden/dot-envrc .envrc
    ```

  * Grant permission to direnv to execute the .envrc file.

    ```shell
    $ direnv allow
    ```

* Install the Python packages required.

  ```shell
  $ poetry install
  ```

* Install the git pre-commit hooks.

  ```shell
  $ pre-commit install
  ```

* Tend the STEAM Garden!

------------------------------------------------------------------------------

[-----------------------------INTERNAL LINKS-----------------------------]: #

[#1]: #1-setup-files

[#2]: #2-setting-up-the-repository
