# Unix CLI

## Shell: Zsh

Zsh is a shell for Unix.

Configuration file: [`.zshrc`](https://github.com/patrick-5546/dotfiles/blob/main/dot_zshrc.tmpl).

Resources:

- [zsh: Syntax Highlighting, vi-mode, Autocomplete, more](https://www.youtube.com/watch?v=eLEo4OQ-cuQ)

### Syntax Highlighting

[Zsh-syntax-highlighting](https://github.com/zsh-users/zsh-syntax-highlighting) brings syntax highlighting to Zsh.
Known commands and aliases are green, unknown are red.

### Vi Mode

I use vi mode to bring vim keybindings to Zsh. To improve the experience, I also added vim keybindings to the tab complete menu,
changed the cursor shape for different modes, and mapped `jk` to exit insert mode.

## Software

[grm](https://github.com/jsnjack/grm) is a basic package manager for GitHub releases.
I use a fork of it in my installation script because it is lightweight, fast, doesn't require sudo permissions,
and works on both MacOS and Linux.

Installation script: [`run_install-unix.sh.tmpl`](https://github.com/patrick-5546/dotfiles/blob/main/run_install-unix.sh.tmpl).

### Atuin

[Atuin](https://github.com/atuinsh/atuin) enhances shell history, saving additional information such as execution time and exit code.
It can even synchronize history between machines!
I mainly use it to interactively search through my command history, replacing ++ctrl+r++.

Configuration files:

- [`.config/atuin/config.toml`](https://github.com/patrick-5546/dotfiles/blob/main/dot_config/atuin/config.toml)

### Bat

[Bat](https://github.com/sharkdp/bat) is an alternative to `cat` with syntax highlighting and Git integration.

### Bpytop

[Bpytop](https://github.com/aristocratos/bpytop) is a detailed and aesthetic CLI resource monitor.

Configuration file: [`.config/bpytop/bpytop.conf`](https://github.com/patrick-5546/dotfiles/blob/main/dot_config/bpytop/bpytop.conf).

### Dust

[Dust](https://github.com/bootandy/dust) is an alternative to `du` that is more intuitive, visualizing disk usage.
