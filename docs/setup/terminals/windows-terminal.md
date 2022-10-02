# Windows Terminal

Windows Terminal is a terminal application to access shells such as PowerShell, WSL distributions, and SSH all in one place.

It can be customized aesthetically and functionally to the moon:

- Aesthetically, there are countless resources online to serve as a starting point.
- Functionality, I went through each setting and customized them based on what I was familiar with (Ubuntu terminal, keybindings from my Vim configuration).

## Demo

![Terminal Demo](../../assets/terminal_demo.gif)

## Setup

1. Install a [Nerd Font](https://www.nerdfonts.com/font-downloads)
    - The fonts I use can be found in `windows/fonts/` of my setup repository (currently I only use FiraCode)

2. My settings, themes, and profiles can be found in `reference_dotfiles/windows_terminal/windows_terminal_settings.json`
   of the dotfiles repository
    - The icons I use can be found in `windows/icons/` of my setup repository

3. See the [common](../cli/common-cli.md) and [windows](../cli/windows-cli.md) CLI pages for details on my Windows CLI configuration

## Shortcuts

I have highlighted a few of the shortcuts that I regularly use. The shortcuts with bolded descriptions are ones I customized.
All the available shortcuts are listed in the `Actions` tab of the settings page.

| Shortcut     | Description                          |
| ----------- | ------------------------------------ |
| ++ctrl+shift+p++ | Toggle command palette (same as VS Code) |
| ++alt+shift+d++ | Pane: duplicate |
| ++alt++ + ++h++ / ++j++ / ++k++ / ++l++ | **Pane: navigate (from my tmux configuration)** |
| ++ctrl+q++ | **Pane: close** |
| ++ctrl+shift+space++ | Tab: open tab selector dropdown |
| ++ctrl+shift++ + *#* | Tab: open profile *#* from tab selector |
| ++ctrl+t++ | **Tab: duplicate (from Microsoft Edge)** |
| ++ctrl+tab++ | Tab: cycle forwards (same as Microsoft Edge) |
| ++ctrl+w++ | **Tab: close (from Microsoft Edge)** |
| ++ctrl+shift+w++ | **Windows: close (from Microsoft Edge)** |

!!! info "What are panes?"

    A tab can be split into multiple panes, enabling you to run commands right next to each other.
    Check out the [documentation page on panes](https://docs.microsoft.com/en-us/windows/terminal/panes) to learn more.

## Resources

- [Complete Nerd Fonts Release](https://github.com/ryanoasis/nerd-fonts/releases/tag/v2.1.0)
- [Windows Terminal Color Schemes](https://www.thomasmaurer.ch/2020/06/my-windows-terminal-color-schemes/)
- [Windows Terminal Documentation](https://docs.microsoft.com/en-us/windows/terminal/)
- [Windows Terminal 2.0 Roadmap](https://github.com/microsoft/terminal/blob/main/doc/terminal-v2-roadmap.md)
- [Windows Terminal specify a starting directory for a SSH profile](https://docs.microsoft.com/en-us/windows/terminal/tutorials/ssh#specify-starting-directory)
- [Windows Terminal open tab/pane in the current directory](https://docs.microsoft.com/en-us/windows/terminal/tutorials/new-tab-same-directory)

## Relevant Files in My Repositories

### [Dotfiles](https://github.com/patrick-5546/dotfiles)

- `reference_dotfiles/windows_terminal/windows_terminal_settings.json`

### [Setup](https://github.com/patrick-5546/setup) (Old)

- `windows/fonts/`
- `windows/icons/`
- `windows/windows_terminal_settings.json`

--8<-- "includes/abbreviations.md"
