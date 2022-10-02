# Common CLI

I use [chezmoi](https://github.com/twpayne/chezmoi) to manage my dotfiles and installation scripts across computers, OS's, and shells.
Its installation instructions can be found in [my dotfiles repository](https://github.com/patrick-5546/dotfiles)'s README.

## Software

### Fzf

[Fzf](https://github.com/junegunn/fzf) is an interactive filer for command line that can be used for any list.
I mainly use it to search through my command history, replacing ++ctrl+r++.

Relevant configuration files: [`.config/fzf/completion.zsh`](https://github.com/patrick-5546/dotfiles/blob/main/dot_config/fzf/completion.zsh),
[`.config/fzf/key-bindings.zsh`](https://github.com/patrick-5546/dotfiles/blob/main/dot_config/fzf/key-bindings.zsh).

### Git

See [Contributing to a Git Repository](../../reference/git/git_contributing.md) and [Git Commands](../../reference/git/git_commands.md)
for my notes on Git.

Relevant configuration file: [`.gitconfig`](https://github.com/patrick-5546/dotfiles/blob/main/dot_gitconfig.tmpl).

#### Git CLI

#### Delta

### Neovim

TODO: move to IDE page.

Relevant configuration files: [`.config/nvim/init.vim`](https://github.com/patrick-5546/dotfiles/blob/main/dot_config/nvim/init.vim)
which is used for my Unix CLI and identical to [`AppData/Local/nvim/init.vim`](https://github.com/patrick-5546/dotfiles/blob/main/AppData/Local/nvim/init.vim)
which is used for my Windows CLI. They both source [`.vimrc`](https://github.com/patrick-5546/dotfiles/blob/main/dot_vimrc).

### Starship

[Starship](https://starship.rs) is a minimal, blazing-fast, and customizable prompt for any shell.
Since it is compatible with all major operating systems, I can use the same configuration file for all my Windows Terminal shells.

Relevant configuration file: [`.config/starship.toml`](https://github.com/patrick-5546/dotfiles/blob/main/dot_config/starship.toml).

## Aliases

Imported at the bottom, windows git aliases from module.

Relevant configuration files: [`.config/zsh/aliases.zsh`](https://github.com/patrick-5546/dotfiles/blob/main/dot_config/zsh/aliases.zsh)
for Unix, [`Documents/PowerShell/aliases.ps1`](https://github.com/patrick-5546/dotfiles/blob/main/Documents/PowerShell/aliases.ps1)
for Windows.

### Functions

Imported at the top, used by aliases or other functions.

Relevant configuration files: [`.config/zsh/functions.zsh`](https://github.com/patrick-5546/dotfiles/blob/main/dot_config/zsh/functions.zsh)
for Unix, [`Documents/PowerShell/functions.ps1`](https://github.com/patrick-5546/dotfiles/blob/main/Documents/PowerShell/functions.ps1) for Windows.
