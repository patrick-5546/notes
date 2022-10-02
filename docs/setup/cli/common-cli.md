# Common CLI

I use [chezmoi](https://github.com/twpayne/chezmoi) to manage my dotfiles and installation scripts across operating
systems and shells.
The installation instructions can be found in [my dotfiles repository](https://github.com/patrick-5546/dotfiles)'s README.

## Software

### Fzf

### Git

#### Git CLI

#### Delta

### Neovim

### Shell

#### Aliases

Imported at the bottom, windows git aliases from module

#### Functions

Imported at the top

### Starship

[Starship](https://starship.rs) is a minimal, blazing-fast, and customizable prompt for any shell.
Since it is compatible with all major operating systems, I can use the same configuration file for all my Windows Terminal shells.

## Relevant Files in My [Dotfiles Repository](https://github.com/patrick-5546/dotfiles)

| File Purpose | File PowerShell uses | File Zsh uses |
| --------- | -------------------- | ------------- |
| Fzf | `dot_config/fzf/completion.zsh`, `dot_config/fzf/key-bindings.zsh` | same as PowerShell |
| Git | `dot_gitconfig` | same as PowerShell |
| Neovim | `AppData/Local/nvim/init.vim`, `dot_vimrc` | `dot_config/nvim/init.vim`, `dot_vimrc` |
| Shell Aliases | `dot_config/zsh/aliases.zsh` | `Documents/PowerShell/aliases.ps1` |
| Shell Functions | `dot_config/zsh/functions.zsh` | `Documents/PowerShell/functions.ps1` |
| Starship | `dot_config/starship.toml` | same as PowerShell |
