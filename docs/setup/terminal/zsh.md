# Zsh Setup

Zsh is a shell for Linux (and thus WSL). My setup repository contains scripts that installs my packages, plugins, and configuration files.

## My Packages, Plugins, and Configuration Files

| Package/Plugin/File | Description |
| -------------- | ----------- |
| [Oh My Posh](https://ohmyposh.dev/docs/) | Theme engine |
| [Oh My Zsh](https://github.com/ohmyzsh/ohmyzsh) | Zsh framework for plugins and themes |
| [diff-so-fancy](https://github.com/so-fancy/diff-so-fancy) | Human readable \[git\] diffs |
| [enhancd](https://github.com/b4b4r07/enhancd) | Make `cd` interfactive |
| [fzf](https://github.com/junegunn/fzf) | Interactive list filter: files, command history, processes, etc. |
| [ripgrep](https://github.com/BurntSushi/ripgrep) | Faster recursive search by ignoring files that are hidden (name starts with `.`) or in a `.gitignore` file |
| `.vimrc` | Configuration file for Vim |
| `.zshrc` | Configuration file for Zsh |
| `~/.zshrc.local` | `.zshrc` sources this, for machine-specific Zsh setup (untracked by setup repository) |

## Setup

!!! tip ""
    Run commands from the home directory (`cd ~`)

1. Clone my setup repository

    ``` sh
    git clone --depth=1 https://github.com/patrick-5546/setup.git ~/.setup
    ```

2. Check for existing `.zshrc` and `.vimrc` configuration files

    ``` sh
    ls -A
    ```

3. Delete/rename any existing configuration files

    ``` sh
    rm .zshrc  # delete .zshrc
    mv .vimrc .vimrc.old  # rename .vimrc to .vimrc.old
    ```

4. Run installation script

    === "If you have root (sudo) access"

        ``` sh
        ./.setup/install.sh
        ```

    === "If you don't have root (sudo) access"

        ``` sh
        ./.setup/install_no_sudo.sh
        ```

    ??? info "Running without root access"
        Without root access, the script won't be able to install Zsh, Oh My Posh, or ripgrep. If you are
        lucky, Zsh and/or ripgrep may already be installed on your machine.

        Workaround for Oh My Posh: install in `~/.local/bin`

        ``` sh
        mkdir -p ~/.local/bin
        wget https://github.com/JanDeDobbeleer/oh-my-posh/releases/latest/download/posh-linux-amd64 -O ~/.local/bin/oh-my-posh
        sudo chmod +x ~/.local/bin/oh-my-posh
        ```

        - If `oh-my-posh --version` is not working in a new terminal, may need to manually add `~/.local/bin` to the `$PATH` environment variable
            1. Check with `echo $PATH | grep ~/.local/bin`
            2. Add to path by adding `export PATH=$PATH:~/.local/bin` to your `~/.zshrc.local` file

    ??? tip "Installing ripgrep in Ubuntu 18.04"
        ripgrep isn't in Ubuntu 18.04, so `sudo apt-get install ripgrep` in `install.sh` won't work

        - Workaround: [install ripgrep manually](https://github.com/BurntSushi/ripgrep/issues/1232#issuecomment-762898478)

5. Make Zsh the default shell

    ``` sh
    chsh -s $(which zsh)
    ```

## Relevant Files in My [Setup Repository](https://github.com/patrick-5546/setup)

- Everything except `windows/`

## Resources

- [Oh My Zsh Plugins](https://github.com/ohmyzsh/ohmyzsh/tree/master/plugins)
