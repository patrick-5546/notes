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
See my Winget documentation [here](../software/windows-software.md#winget).

Installation script: [`run_install-windows.ps1`](https://github.com/patrick-5546/dotfiles/blob/main/run_install-windows.ps1).

Some of my favorite software include:

- [Bitwarden](https://github.com/bitwarden/clients): password manager that has apps for all my devices
- [Komorebi](https://github.com/LGUG2Z/komorebi): tiling window manager
- [Microsoft To Do](https://www.microsoft.com/en-ca/microsoft-365/microsoft-to-do-list-app): task management; I especially like the "My Day" list
- [Mozilla Thunderbird](https://www.thunderbird.net/en-US/): email client, as Outlook doesn't play nice with Gmail
- [NanaZip](https://github.com/M2Team/NanaZip): file archiver with a modern UI, forked from 7-Zip
- [OneNote](https://www.microsoft.com/en-ca/microsoft-365/onenote/digital-note-taking-app): note taking, whether typed, handwritten, or annotated
- [VLC](https://www.videolan.org/): video player with powerful features that can play any type of video
- [WizTree](https://diskanalyzer.com/): quick and visual disk space analyzer

--8<-- "includes/abbreviations.md"
