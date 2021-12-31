# PowerShell Setup

PowerShell with file icons, autocomplete, and a custom theme. Followed the setup guide in the [Resources](./powershell.md#resources) section

## Setup

1. Download the PowerShell app from the Microsoft Store
    - This app is the latest version of PowerShell and includes the PSReadLine Module for autocomplete

2. Install the requirements

    1. Install oh-my-posh

        ``` powershell
        winget install --id=JanDeDobbeleer.OhMyPosh
        ```

    2. Install Terminal Icons

        ``` powershell
        Install-Module -Name Terminal-Icons -Repository PSGallery
        ```

3. In the PowerShell profile, update absolute path to Oh My Posh theme if necessary, and comment out the `Clear-Host` command at the end for debugging purposes

    ``` powershell title="windows\Microsoft.PowerShell_profile.ps1"
    oh-my-posh --init --shell pwsh --config "$env:USERPROFILE\Programming\git_projects\.setup\poshthemes\atomic_tweak_windows.json" | Invoke-Expression
    ```

4. Symbolic link the PowerShell profile to the `Powershell` directory in an Administrator PowerShell prompt

    ``` powershell
    New-Item -ItemType SymbolicLink -Path "$env:USERPROFILE\Documents\PowerShell\Microsoft.PowerShell_profile.ps1" -Value "$env:USERPROFILE\Programming\git_projects\.setup\windows\Microsoft.PowerShell_profile.ps1"
    ```

    ??? bug "PSReadLine feature is unsupported"
        Install the latest release of PSReadLine (check [here](https://github.com/PowerShell/PSReadLine/releases)). In
        December 2021, the latest release was v2.2.0-beta4:

        ``` powershell
        Install-Module -Name PSReadLine -RequiredVersion 2.2.0-beta4 -AllowPrerelease
        ```

5. To get rid of the startup messages before prompt, you can uncomment the `Clear-Host` command at the end of the Powershell profile

??? question "Why symbolic link?"
    See my reasoning in the [IDE](../ide.md#why-symbolic-link) page.

## Relevant Files in My [Setup Repository](https://github.com/patrick-5546/setup)

- `poshthemes/atomic_tweak_windows.json`
- `windows/Microsoft.PowerShell_profile.ps1`

## Resources

- The PowerShell profile is from [this setup guide](https://www.hanselman.com/blog/my-ultimate-powershell-prompt-with-oh-my-posh-and-the-windows-terminal)
    - Refer to the [accompanying video](https://www.youtube.com/watch?v=VT2L1SXFq9U&list=LL&index=21) that walks through the article if any issues arise
