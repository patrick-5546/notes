# Windows CLI

## Shell: PowerShell 7

PowerShell is a shell for Windows. PowerShell 7 is not the version that Windows includes, and will have to be installed.

Configuration file: [`Documents/PowerShell/Microsoft.PowerShell_profile.ps1`](https://github.com/patrick-5546/dotfiles/blob/main/Documents/PowerShell/Microsoft.PowerShell_profile.ps1).

### PSReadLine

This module brings the Unix CLI experience to PowerShell. I use it to add Vi mode, autocomplete options using ++tab++, and search for commands using ++ctrl+r++.

## Software

[UniGetUI](https://github.com/marticliment/UniGetUI) is a GUI for Windows package managers.
I primarily use it to install software using [WinGet](https://github.com/microsoft/winget-cli), the official Windows package manager.
The CLI of WinGet is pretty complex, so I find UniGetUI useful for managing it in an intuitive way.

The complete list of apps I install using UniGetUI can be found [here](https://github.com/patrick-5546/dotfiles/tree/main/reference_dotfiles/wingetui).

--8<-- "includes/abbreviations.md"
