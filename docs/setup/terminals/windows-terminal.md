# Windows Terminal

Windows Terminal is a terminal application to access shells such as PowerShell, WSL distributions, and SSH all in one place.

It can be customized aesthetically and functionally to the moon:

- Aesthetically, there are countless resources online to serve as a starting point.
- Functionality, I went through each setting and customized them based on what I was familiar with (Ubuntu terminal, keybindings from my Vim configuration).

## Showcase

This is what my Windows Terminal configuration looked like when I was still using the [setup repository](https://github.com/patrick-5546/setup).
Currently my configuration looks a lot more like my [Unix terminal configuration](./unix-terminal.md#showcase).

![Windows Terminal Demo](../../assets/windows_terminal_demo.gif)

## Setup

1. Install a [Nerd Font](https://www.nerdfonts.com/font-downloads)
    - The fonts I use can be found in [`windows/fonts/`](https://github.com/patrick-5546/setup/tree/master/windows/fonts)
      of my setup repository (currently I only use FiraCode)

2. My settings, themes, and profiles can be found in [`reference_dotfiles/windows_terminal/windows_terminal_settings.json`](https://github.com/patrick-5546/dotfiles/blob/main/reference_dotfiles/windows_terminal/windows_terminal_settings.json)
   of the dotfiles repository
    - The icons I use can be found in [`windows/icons/`](https://github.com/patrick-5546/setup/tree/master/windows/icons) of my setup repository

## Shortcuts

I have highlighted a few of the shortcuts that I regularly use. The shortcuts with the "Similarity" column italicized
are ones that I modified from their default values.
All the available shortcuts are listed in the `Actions` tab of the settings page.

| Shortcut                                | Description                   | Similarity                                   |
| --------------------------------------- | ----------------------------- | -------------------------------------------- |
| ++ctrl+w++                              | Close pane                    | *Microsoft Edge*                           |
| ++ctrl+shift+w++                        | Close window                  | *Microsoft Edge*                           |
| ++alt+shift+d++                         | Duplicate pane                |                                              |
| ++ctrl+shift+d++                        | Duplicate tab                 |                                              |
| ++alt++ + ++j++ / ++h++ / ++l++ / ++k++ | Move focus down/left/right/up | [*My tmux setup*](./unix-terminal.md#tmux) |
| ++ctrl+tab++                            | Next tab                      | Microsoft Edge                               |
| ++ctrl+shift+space++                    | Open new tab dropdown         |                                              |
| ++ctrl+shift++ + *#*                    | Switch to tab, index:*#*      |                                              |
| ++ctrl+shift+p++                        | Toggle command palette        | VS Code                                      |

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

--8<-- "includes/abbreviations.md"
