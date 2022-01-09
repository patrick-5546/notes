# :material-microsoft-windows: WSL

## Backing up and Restoring WSL Distributions

1. Export a WSL distribution for backup/migration from PowerShell

    ``` powershell
    wsl --export <distribution_name> <filename>
    ```

2. To import a WSL distribution from PowerShell

    ``` powershell
    wsl --import <distribution_name> <install_location> <filename>
    ```

3. This new WSL distribution will start as the root user. To start as another user, add the following to `/etc/wsl.conf` from inside the distribution

    ``` yaml linenums="1" title="wsl.conf"
    [user]
    default=<username>
    ```

4. `#!powershell wsl --shutdown` from PowerShell and restart to see the change

## More WSL Commands

| Command | Description |
| ------- | ----------- |
| `wsl -l -v` | List WSL distributions along with their state and version |
| `wsl -t <distgribution_name>` | Terminate/shut down a WSL distribution |
| `wsl --unregister <distribution_name>` | Unregisters WSL distribution and deletes root filesystem |

- `wsl --help` to see all WSL commands and their descriptions

## Commands Inside WSL Distributions

- Sign in to Git using the Git Credential Manager in Windows

    ``` sh
    git config --global credential.helper "/mnt/c/Program\ Files/Git/mingw64/libexec/git-core/git-credential-manager-core.exe"
    ```

- Open a WSL file/directory using the Windows default program
    - For example: File Explorer for directories, Excel for CSV files

    ``` sh
    wslview <file_or_directory>
    ```

## Resources

- [Install WSL](https://docs.microsoft.com/en-us/windows/wsl/install)
- [Export and import WSL distributions](https://winaero.com/export-import-wsl-linux-distro-windows-10/)
- [Change default user in WSL 2](https://github.com/microsoft/WSL/issues/4276#issuecomment-553367389)
- [Get started using Git on WSL](https://docs.microsoft.com/en-us/windows/wsl/tutorials/wsl-git)

--8<-- "includes/abbreviations.md"
