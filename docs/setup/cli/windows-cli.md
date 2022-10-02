# Windows CLI

## Shell: PowerShell 7

PowerShell is a shell for Windows.

Configuration file: [`Documents/PowerShell/Microsoft.PowerShell_profile.ps1`](https://github.com/patrick-5546/dotfiles/blob/main/Documents/PowerShell/Microsoft.PowerShell_profile.ps1).

Resources:

- [How to make the ultimate Terminal Prompt on Windows 11](https://www.youtube.com/watch?v=VT2L1SXFq9U&list=LL)

## Software

### Package Manager: Chocolatey

[Chocolatey](https://chocolatey.org) is an easy-to-use package manager with a large and up-to-date library.
I didn't use Winget, the official Windows package manager, because being relatively young it does not contain all the packages that I want.
I will likely migrate to Winget once it does. See my Winget documentation [here](../software/windows-software.md#winget).

Installation script: [`install.ps1`](https://github.com/patrick-5546/dotfiles/blob/main/install.ps1).

### Modules

#### git-aliases

[powershell-git-aliases](https://github.com/gluons/powershell-git-aliases) provides partial Git aliases from
[Oh My Zsh's git plugin](https://github.com/ohmyzsh/ohmyzsh/tree/master/plugins/git).

#### PSFzf

[PSFzf](https://github.com/kelleyma49/PSFzf) brings the power of [FzF](./common-cli.md#fzf) to PowerShell.
