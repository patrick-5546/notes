# Other Windows Software

## Chris Titus Tech's Windows Utility

[Winutil](https://github.com/ChrisTitusTech/winutil) is meant to streamline installs, debloat with tweaks,
troubleshoot with config, and fix Windows updates.
To run, paste the following command into an Administrator PowerShell prompt:

``` powershell
iwr -useb https://christitus.com/win | iex
```

Resources:

- [The best Windows tool for 2022](https://www.youtube.com/watch?v=tPRv-ATUBe4)

## Package Manager

Using a package manager such as winget allows software to be quickly and easily installed,
upgraded, and uninstalled using the terminal. Winget is relatively new and thus does not yet support
as many packages as other package managers. However, it is quickly growing, built into Windows 11, and
compatible with other package managers and the standard Windows Installer. I have been using Chocolatey to get
packages that are not yet available on winget, but this has become increasingly rare.

??? info "Useful applications I installed using a package manager"
    | Application Name | Description |
    | -------------- | ----------- |
    | 7zip | Compress and extract files of different formats |
    | Microsoft PowerToys | Set of utilities for customizing Windows |
    | TeamViewer | Remote desktop software |
    | TreeSize Free | Disk space manager, shows sizes of folders including all subfolders |
    | VLC | Media player supporting most of media codecs and video formats; basic video editor |

### Winget quick reference

- Works with applications installed via other means
- By default, opens the installer window just like double clicking on an installation file
    - `-h` will attempt to run command without the needs for user input

| Command     | Description                          |
| ----------- | ------------------------------------ |
| `winget search <query>` | Search for an app matching the query |
| `winget install --id <app_id>` | Install app |
| `winget list` | List all installed apps (outdated apps have something in the `Available` column |
| `winget list <query>` | List installed apps matching the query |
| `winget upgrade --id <app_id>` | Upgrade app |
| `winget upgrade --all` | Upgrade all apps |
| `winget uninstall --id <app_id>` | Uninstall app |

Resources:

- [winget command reference and examples](https://docs.microsoft.com/en-us/windows/package-manager/winget/#commands)
- [Search winget packages, generate command that installs the desired packages](https://winstall.app/)

### Chocolatey quick reference

Run the following commands in an Administrator PowerShell prompt:

- `-y` confirms all prompts so that the command runs without the need for user input

| Command     | Description                          |
| ----------- | ------------------------------------ |
| `choco install <package1> <package2> -y` | Install packages |
| `choco list -l` | List packages installed using Chocolatey |
| `choco pin add -n <package>` | Keep package at current version |
| `choco pin list` | List pinned packages |
| `choco pin remove -n <package>` | Allow package to be upgraded |
| `choco outdated` | List outdated packages |
| `choco upgrade <package> -y` | Upgrade package |
| `choco upgrade all -y` | Upgrade all packages |
| `choco uninstall <package> -y` | Uninstall package |

Resources:

- [Installing Chocolatey](https://chocolatey.org/install)
- [Search Chocolatey packages](https://community.chocolatey.org/packages)
- [Chocolatey command reference and examples](https://docs.chocolatey.org/en-us/choco/commands/)

## Microsoft Store

All applications, including those from the Microsoft Store, can be managed using winget.
However, it is easier to manage Microsoft Store applications using the Microsoft Store app.

??? info "Useful applications I installed using the Microsoft Store"
    | Application Name | Description |
    | -------------- | ----------- |
    | EarTrumpet | Control the volume of each application (and system sounds) individually |
    | Microsoft To Do | To do list |
    | OneNote (for Windows 10) | Note-taking |
    | Snip & Sketch | Take, annotate, and save screenshots |
