# :material-linux:/:material-apple: Linux/MacOS Commands

[Linuxize.com](https://linuxize.com/) has some amazing guides for common Linux/MacOS commands and tasks.
If their site does not have cover the desired content, `man <command>` to view the full documentation of a command.

## [Linuxize Basic Linux Commands](https://linuxize.com/post/basic-linux-commands/)

- Covers man, pwd, cd, ls, cat, touch, mkdir, ln, rm, cp, mv, apt, dnf, chmod, chown, sudo, useradd, passwd, userdel, groupadd, groupdel, and usermod

## alias

Aliases are custom commands that map to a longer command.

| Command     | Description                          |
| ----------- | ------------------------------------ |
| `alias <alias>="<command>"` | Create an alias |
| `which <alias/command>` | Locate an alias/command |
| `alias` | View the mappings of all aliases |

My shell aliases can be found in [`aliases.zsh`](https://github.com/patrick-5546/dotfiles/blob/main/dot_config/zsh/aliases.zsh).

Resources:

- [Linuxize alias guide](https://linuxize.com/post/how-to-create-bash-aliases/)

## du

Estimates disk usage of the given files or directories.

| Command     | Description                          |
| ----------- | ------------------------------------ |
| `du -ha <file/directory>` | Get size of each file within the directory recursively |
| `du -h --max-depth=1 <directory>` | Get size of directories up to the first level |
| `du -hs` | Get only the size of the current working directory |

Resources:

- [Linuxize du guide](https://linuxize.com/post/du-command-in-linux/)

## find

Recursively searches for files and directories.

| Command | Description |
| ------- | ----------- |
| `find -type f -iname <filename>` | Search for files by name, ignoring case |
| `find -type f -name '*.<file_extension>'` | Search for files by extension |

Resources:

- [Linuxize find guide](https://linuxize.com/post/how-to-find-files-in-linux-using-the-command-line/)

## less

Read contents of a file or command output quickly and without filling up terminal.

| Command | Description |
| ------- | ----------- |
| `less <filename>` | Read the contents of a file |
<!-- markdownlint-disable-next-line MD033 -->
| `<command> | less` | Read the standard output (what would be printed to the terminal) of `<command>` |

??? info "Commands inside less"

    | Command | Description |
    | ------- | ----------- |
    | `h` | Display help |
    | `q` | Exit |
    | `g` | Go to first line of file |
    | *#*`g` | Go to line *#* |
    | `G` | Go to last line of file |
    | `j`/`k` | Move forward and backward by line |
    | `f`/`b` | Move forward and backward by window |
    | `-N` | Toggle line numbers |
    | `-S` | Toggle chopping long lines |
    | `/<string>` | Search for `<string>` |
    | `n`/`N` | Navigate between search matches |

Resources:

- [Linuxize less guide](https://linuxize.com/post/less-command-in-linux/)

## screen

I use screen to perform long-running tasks on a remote machine. It enables me to connect and disconnect from the machine
(i.e. via [SSH](./ssh.md)) without exiting the command.

| Command     | Description                          |
| ----------- | ------------------------------------ |
| `screen -S <session_name>` | Start a named screen session |
| `screen -d` | Detach from current screen |
| ++ctrl+alt++ then ++d++ | Detach from current screen when a command is running |
| `screen -ls` | List running screens and their session IDs |
| `screen -r <session_id>` | Reattach to screen |
| `screen -d -r <session_id>` | Reattach to screen from inside another screen |
| `exit` | Terminate current screen |

??? bug "`screen` in WSL"

    Error Message

    ``` console
    $ screen
    Cannot make directory '/run/screen': Permission denied
    ```

    To Fix

    1. Create an alternate screen directory with the appropriate permissions
    ```
    mkdir ~/.screen && chmod 700 ~/.screen
    ```
    2. Point the `SCREENDIR` environment variable to that directory
    ``` shell title=".bashrc file or equivalent"
    export SCREENDIR=$HOME/.screen
    ```

Resources:

- [Linuxize screen guide](https://linuxize.com/post/how-to-use-linux-screen/)

## Additional Guides

- [Linuxize shebang guide](https://linuxize.com/post/bash-shebang/) - run script without having to specify the interpreter
- [Linuxize add to the PATH environment variable](https://linuxize.com/post/how-to-add-directory-to-path-in-linux/)

--8<-- "includes/abbreviations.md"
