# :material-linux: Linux Commands

Linux commands that I regularly use.

## `alias`

Aliases are custom commands that map to a longer command.

| Command     | Description                          |
| ----------- | ------------------------------------ |
| `alias <alias>="<command>"` | Create an alias |
| `which <alias/command>` | Locate an alias/command |
| `alias` | View the mappings of all aliases |

??? quote "My aliases"
    Run the commands to see what they do

    Oh My Zsh creates a lot of useful aliases, here are some that I regularly use:

    ``` shell
    alias l='ls -lah'
    alias ll='ls -lh'
    alias md='mkdir -p'
    alias rd='rmdir'
    ```

    - Aliases that I use from the Git plugin are detailed in the [Commands page](./git/git_commands.md#oh-my-zsh-git-plugin-aliases)

    Aliases that I defined myself

    ``` shell title="Section of my .zshrc file"
    alias cls='clear'
    alias h='history'
    alias lt='ls -lahrt'
    alias llt='ls -lhrt'
    ```

## `screen`

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

## Resources

- Walkthroughs of common Linux commands can be found by searching [linuxize.com](https://linuxize.com/).
- `man <command>` to view the full documentation of a command.

--8<-- "includes/abbreviations.md"
