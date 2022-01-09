# Terminal Setup

## Demo

![Terminal Demo](../../assets/terminal_demo.gif)

## Software Stack

### Windows Terminal

Windows Terminal is a terminal application to access shells such as PowerShell, WSL distributions, and SSH all in one place.

It can be customized aesthetically and functionally to the moon:

- Aesthetically, there are countless resources online to serve as a starting point.
- Functionality, I went through each setting and customized them based on what I was familiar with (Ubuntu terminal, keybindings from my Vim configuration).

### Oh My Posh

Oh My Posh is a theme engine for any shell. Since it is compatible with all the major operating systems,
I can use the same custom theme (based on [atomic](https://ohmyposh.dev/docs/themes#atomic))
for all my Windows Terminal shells.

!!! tip "Customizing Oh My Posh themes to use in Windows Terminal"
    - I would recommend against right-aligning segments, as their formatting gets messed up when resizing panes.
    - To open tabs/panes in the current directory, add `#!json "osc99": true,` to your Oh My Posh theme.

## Setup

1. Clone my setup repository

    ``` powershell
    git clone --depth=1 https://github.com/patrick-5546/setup.git "$env:USERPROFILE\git_projects\.setup"
    ```

2. Install fonts that support symbols used by Oh My Posh (i.e., [Nerd Fonts](https://www.nerdfonts.com/font-downloads))
    1. My fonts can be extracted from `windows\fonts.zip`

3. My settings, themes, and sample profiles can be found in `windows\windows_terminal_sample_settings.json`

4. The [PowerShell](./powershell.md) and [Zsh](./zsh.md) pages detail how I setup these shells to use in Windows Terminal
    - [Add Git Bash to Windows Terminal](https://stackoverflow.com/a/57369284)

## Windows Terminal Shortcuts

I have highlighted a few of the shortcuts that I regularly use. The shorcuts with italicized descriptions are ones I customized.
All the available shortcuts are listed in the `Actions` tab of the settings page.

| Shortcut     | Description                          |
| ----------- | ------------------------------------ |
| ++ctrl+shift+p++ | Toggle command palette (same as VS Code) |
| ++ctrl+shift+w++ | *Close windows (from Microsoft Edge)* |
| ++ctrl+shift+space++ | Open new tab dropdown |
| ++ctrl+shift++ + *#* | Open profile *#* in a new tab |
| ++ctrl+t++ | *Duplicate current tab (from Microsoft Edge)* |
| ++ctrl+tab++ | Cycle forwards between tabs (same as Microsoft Edge) |
| ++ctrl+w++ | *Close tab (from Microsoft Edge)* |
| ++alt+shift+d++ | Split pane the long way |
| ++ctrl++ + ++h++/++j++/++k++/++l++ | *Move between panes (from my IDE configuration)* |
| ++ctrl+q++ | *Close pane* |

!!! info "What are panes?"

    A tab can be split into multiple panes, enabling you to run commands right next to each other.
    Check out the [documentation page on panes](https://docs.microsoft.com/en-us/windows/terminal/panes) to learn more.

## Relevant Files in My [Setup Repository](https://github.com/patrick-5546/setup)

- `windows/fonts.zip`
- `windows/windows_terminal_sample_settings.json`

## Resources

- [Windows Terminal Color Schemes](https://www.thomasmaurer.ch/2020/06/my-windows-terminal-color-schemes/)
- [Windows Terminal Documentation](https://docs.microsoft.com/en-us/windows/terminal/)
- [Windows Terminal 2.0 Roadmap](https://github.com/microsoft/terminal/blob/main/doc/terminal-v2-roadmap.md)
- [Windows Terminal specify a starting directory for a SSH profile](https://docs.microsoft.com/en-us/windows/terminal/tutorials/ssh#specify-starting-directory)
- [Windows Terminal open tab/pane in the current directory](https://docs.microsoft.com/en-us/windows/terminal/tutorials/new-tab-same-directory)
    - [Solution for Zsh](https://github.com/microsoft/terminal/issues/3158#issuecomment-986826132)
- [Oh My Posh documentation and included themes](https://ohmyposh.dev/docs)
- [Complete Nerd Fonts Release](https://github.com/ryanoasis/nerd-fonts/releases/tag/v2.1.0)
- [Powershell -NoLogo parameter render spaces between blocks](https://github.com/JanDeDobbeleer/oh-my-posh/issues/172#issuecomment-912132691)
