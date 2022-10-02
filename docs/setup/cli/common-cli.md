# Common CLI

I use [chezmoi](https://github.com/twpayne/chezmoi) to manage my dotfiles and installation scripts across computers, OS's, and shells.
Its installation instructions can be found in [my dotfiles repository](https://github.com/patrick-5546/dotfiles)'s README.

## Software

### Fzf

[Fzf](https://github.com/junegunn/fzf) is an interactive filer for command line that can be used for any list.
I mainly use it to search through my command history, replacing ++ctrl+r++.

Configuration files: [`.config/fzf/completion.zsh`](https://github.com/patrick-5546/dotfiles/blob/main/dot_config/fzf/completion.zsh),
[`.config/fzf/key-bindings.zsh`](https://github.com/patrick-5546/dotfiles/blob/main/dot_config/fzf/key-bindings.zsh).

### Git

See [Contributing to a Git Repository](../../reference/git/git_contributing.md) and [Git Commands](../../reference/git/git_commands.md)
for my notes on Git.

Configuration file: [`.gitconfig`](https://github.com/patrick-5546/dotfiles/blob/main/dot_gitconfig.tmpl).

#### Git CLI

[GitHub CLI](https://github.com/cli/cli) brings GitHub functionality such as pull requests and issues to your terminal,
but I only use it to login to GitHub.

#### Delta

[Delta](https://github.com/dandavison/delta) is a syntax-highting pager for git, diff, and grep output.
It makes `git diff` so much easier to understand.

### Starship

[Starship](https://starship.rs) is a minimal, blazing-fast, and customizable prompt for any shell.
Since it is compatible with all major operating systems, I can use the same configuration file across operating systems
to achieve a consistent aesthetic.

Configuration file: [`.config/starship.toml`](https://github.com/patrick-5546/dotfiles/blob/main/dot_config/starship.toml).
