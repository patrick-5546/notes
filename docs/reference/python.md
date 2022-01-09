# :material-language-python: Python

## Conventions

- [PEP 8 styling guideline walkthrough](https://realpython.com/python-pep8/)
    - [Using the flake8 linter](https://flake8.pycqa.org/en/latest/user/invocation.html) - checks for errors (including failing to comply with PEP 8 guidelines
- [Meaning and naming conventions around single and double underscores](https://dbader.org/blog/meaning-of-underscores-in-python)

## Imports

- [Recap on imports, absolute vs relative imports](https://realpython.com/absolute-vs-relative-python-imports/)
- [Python 2 vs 3 imports](https://stackoverflow.com/a/12173406)

## Pip

Package installer.

| Command | Description |
| ------- | ----------- |
| `pip install <package>` | Install the latest version of a package |
| `pip install <package>==<version>` | Install the specified version of a package |
| `pip install -r requirements.txt` | Install the packages from a `requirements.txt` file |
| `pip list --outdated` | View outdated packages |
| `pip install --upgrade <package>` | Upgrade the desired packages |
| `pip uninstall <package>` | Uninstall a package |

!!! tip ""
    If pip has not been added to the path, replace `pip` with `python -m pip` in the commands above.

## Pyenv

Easily switch between multiple versions of Python.

- [Installation](https://github.com/pyenv/pyenv#installation)
- [Commands reference](https://github.com/pyenv/pyenv/blob/master/COMMANDS.md)

## Scripting

- Library for powerful, user-friendly command-line parsing: [argparse tutorial](https://docs.python.org/3/howto/argparse.html)

## Virtual Environments

Bundle all the packages and their versions to run an application so that they do not conflict with the globally installed python packages.

1. Create virtual environment directory (suggested name: `.venv`).

    === ":material-microsoft-windows: Windows"

        ```
        py -m venv .venv
        ```

    === ":material-linux: Linux"

        ```
        python3 -m venv .venv
        ```

2. Activate virtual environment. Use the active shell's corresponding `activate` script.

    === ":material-powershell: Windows Powershell"

        ```
        .venv\Scripts\Activate.ps1
        ```

    === ":material-linux: Linux"

        ```
        source .venv/bin/activate
        ```

3. Install the required packages: [pip section](#pip)

4. Create/update the `requirements.txt` file (to record the versions of packages used in the project)

    ```
    pip freeze > requirements.txt
    ```

5. Exit the virtual environment

    ```
    deactivate
    ```

!!! tip "VS Code integration"
    After selecting `.venv/bin/python` to be the Python interpreter, terminals and debuggers will run
    in the virtual environment by default.

### Resources

- [Virtual Environments and Packages](https://docs.python.org/3/tutorial/venv.html)
