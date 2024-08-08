# Common CLI

I use [chezmoi](https://github.com/twpayne/chezmoi) to manage my dotfiles and installation scripts across computers, OS's, and shells.
Its installation instructions can be found in [my dotfiles repository](https://github.com/patrick-5546/dotfiles)'s README.

## Shell

### Aliases

I created aliases for my most frequently used commands, and tried to keep them consistent across operating systems.

Configuration files:

- Unix: [`.config/zsh/aliases.zsh`](https://github.com/patrick-5546/dotfiles/blob/main/dot_config/zsh/aliases.zsh)
- Windows: [`Documents/PowerShell/aliases.ps1`](https://github.com/patrick-5546/dotfiles/blob/main/Documents/PowerShell/aliases.ps1)
- Git (aliases are at the bottom): [`.gitconfig`](https://github.com/patrick-5546/dotfiles/blob/main/dot_gitconfig.tmpl)

### Functions

Various helper functions are used in my shell configuration and aliases files.

Configuration files:

- Unix: [`.config/zsh/functions.zsh`](https://github.com/patrick-5546/dotfiles/blob/main/dot_config/zsh/functions.zsh)
- Windows: [`Documents/PowerShell/functions.ps1`](https://github.com/patrick-5546/dotfiles/blob/main/Documents/PowerShell/functions.ps1)

## Software

### Fd

[Fd](https://github.com/sharkdp/fd) is an alternative to `find` that is faster and more intuitive.

### Git

See [Contributing to a Git Repository](../../reference/git/git_contributing.md) and [Git Commands](../../reference/git/git_commands.md)
for my notes on Git.

Configuration file: [`.gitconfig`](https://github.com/patrick-5546/dotfiles/blob/main/dot_gitconfig.tmpl).

#### Git CLI

[GitHub CLI](https://github.com/cli/cli) brings GitHub functionality such as pull requests and issues to your terminal,
but I mainly use it to login to GitHub.

#### Delta

[Delta](https://github.com/dandavison/delta) is a syntax-highting pager for git, diff, and grep output.
It makes `git diff` so much easier to understand.

#### Lazygit

[Lazygit](https://github.com/jesseduffield/lazygit) is a TUI for git that makes viewing diffs and
staging lines (in addition to files) easy.

### Ripgrep

[Ripgrep](https://github.com/BurntSushi/ripgrep) is an alternative to `grep` that is faster and respects your gitignore.

### Lsd

[Lsd](https://github.com/lsd-rs/lsd) is an alternative to `ls` that adds colors, icons, and much more.

### Starship

[Starship](https://starship.rs) is a minimal, blazing-fast, and customizable prompt for any shell.
Since it is compatible with all major operating systems, I can use the same configuration file across operating systems
to achieve a consistent aesthetic.

Configuration file: [`.config/starship.toml`](https://github.com/patrick-5546/dotfiles/blob/main/dot_config/starship.toml).

### Yazi

[Yazi](https://github.com/sxyazi/yazi) is a terminal file manager
that can be used to view files and interactively navigate to directories.

### Zoxide

[Zoxide](https://github.com/ajeetdsouza/zoxide) is an alternative to `cd` that can jump to frequently directories
with just a few letters instead of their entire path.

--8<-- "includes/abbreviations.md"
