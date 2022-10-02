# Windows CLI

## Shell: PowerShell 7

PowerShell with file icons, autocomplete, and a custom theme. Followed the setup guide in the [Resources](#resources) section

### Aliases

I created aliases for my most frequently used commands, and tried to keep them consistent across operating systems.

Configuration file: [`Documents/PowerShell/aliases.ps1`](https://github.com/patrick-5546/dotfiles/blob/main/Documents/PowerShell/aliases.ps1).

### Functions

Various helper functions are used in my shell configuration and aliases files.

Configuration file: [`Documents/PowerShell/functions.ps1`](https://github.com/patrick-5546/dotfiles/blob/main/Documents/PowerShell/functions.ps1).

### Modules

#### PSFzf

[PSFzf](https://github.com/kelleyma49/PSFzf) brings the power of [FzF](./common-cli.md#fzf) to PowerShell.

#### Terminal-Icons

### Resources

- My old PowerShell profile is from [this setup guide](https://www.hanselman.com/blog/my-ultimate-powershell-prompt-with-oh-my-posh-and-the-windows-terminal)
    - Refer to the [accompanying video](https://www.youtube.com/watch?v=VT2L1SXFq9U&list=LL&index=21) that walks through the article if any issues arise
Configuration file: [`Documents/PowerShell/Microsoft.PowerShell_profile.ps1`](https://github.com/patrick-5546/dotfiles/blob/main/Documents/PowerShell/Microsoft.PowerShell_profile.ps1).

## Package Manager: Chocolatey