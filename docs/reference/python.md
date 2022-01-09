# :material-language-python: Python

pyenv, relative/absolute imports (checkout local pathfinding test directory), updating packages, modules, pip

## Virtual Environments

### Motivation

Bundle all the packages [at the versions] necessary to run an application in the project's root directory so that they do not interfere with the globally installed python packages.
For more information, see the [Python Docs](https://docs.python.org/3/tutorial/venv.html#creating-virtual-environments).

### Commands reference

1. Create virtual environment directory (suggested name: `.venv`).

    === ":material-windows: Windows"

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

    === ":octicons-terminal-16: Windows Command Prompt"

        ```
        .venv\Scripts\activate.bat
        ```

    === ":material-linux: Linux"

        ```
        source .venv/bin/activate
        ```

3. Install the required packages

    ??? info "Installation methods"

        1. Installing the packages listed in a `requirements.txt` file

            ```
            pip install -r requirements.txt
            ```

        2. Installing a new package

            ```
            pip install <package_name>
            ```

        3. View outdated packages

            ```
            pip list --outdated
            ```

        4. Upgrading a package

            ```
            pip install <package_name> --upgrade
            ```

4. Create/update the `requirements.txt` file (to record the versions of packages used in the project)

    ```
    pip freeze > requirements.txt
    ```

5. Exit the virtual environment

    ```
    deactivate
    ```

### VS Code integration

After selecting `.venv/bin/python` to be the Python interpreter, terminals and debuggers will run
in the virtual environment.
