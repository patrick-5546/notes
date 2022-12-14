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

[HomeBrew](https://github.com/Homebrew/brew) is an easy-to-use package manager with a large and up-to-date library.
I use it in my installation script because it works on MacOS and any Linux distribution.

Installation script: [`run_install-unix.sh.tmpl`](https://github.com/patrick-5546/dotfiles/blob/main/run_install-unix.sh.tmpl).

Resources:

- [modern-unix](https://github.com/ibraheemdev/modern-unix)

### Bat

[Bat](https://github.com/sharkdp/bat) is an alternative to `cat` with syntax highlighting and Git integration.

### Bpytop

[Bpytop](https://github.com/aristocratos/bpytop) is a detailed and aesthetic CLI resource monitor.

Configuration file: [`.config/bpytop/bpytop.conf`](https://github.com/patrick-5546/dotfiles/blob/main/dot_config/bpytop/bpytop.conf).

### Dust

[Dust](https://github.com/bootandy/dust) is an alternative to `du` that is more intuitive, visualizing disk usage.

### Fd

[Fd](https://github.com/sharkdp/fd) is an alternative to `find` that is faster and more intuitive.

### Ripgrep

[Ripgrep](https://github.com/BurntSushi/ripgrep) is an alternative to `grep` that is faster and respects your gitignore.
