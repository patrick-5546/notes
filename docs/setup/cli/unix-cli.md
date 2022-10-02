# Unix CLI

## Shell: Zsh

Zsh is a shell for Unix.

Configuration file: [`.zshrc`](https://github.com/patrick-5546/dotfiles/blob/main/dot_zshrc.tmpl).

Resources:

- [zsh: Syntax Highlighting, vi-mode, Autocomplete, more](https://www.youtube.com/watch?v=eLEo4OQ-cuQ)

### Aliases

I created aliases for my most frequently used commands, and tried to keep them consistent across operating systems.

Configuration file: [`.config/zsh/aliases.zsh`](https://github.com/patrick-5546/dotfiles/blob/main/dot_config/zsh/aliases.zsh).

### Functions

Various helper functions are used in my shell configuration and aliases files.

Configuration file: [`.config/zsh/functions.zsh`](https://github.com/patrick-5546/dotfiles/blob/main/dot_config/zsh/functions.zsh).

### Syntax Highlighting

[Zsh-syntax-highlighting](https://github.com/zsh-users/zsh-syntax-highlighting) brings syntax highlighting to Zsh.
Known commands and aliases are green, unknown are red.

### Vi Mode

I use vi mode to bring vim keybindings to Zsh. To improve the experience, I also added vim keybindings to the tab complete menu,
changed the cursor shape for different modes, and mapped `jk` to exit insert mode.

## Software

### Package Manager: HomeBrew

[HomeBrew](https://github.com/Homebrew/brew) is an easy-to-use package manager with a large and up-to-date library.
I use it in my installation script because it works on MacOS and any Linux distribution.

Installation file: [`run_install.sh.tmpl`](https://github.com/patrick-5546/dotfiles/blob/main/run_install.sh.tmpl)

### Bat

### Bpytop

Configuration file: [`.config/bpytop/bpytop.conf`](https://github.com/patrick-5546/dotfiles/blob/main/dot_config/bpytop/bpytop.conf).

### Dust

### Fd

### Ripgrep
