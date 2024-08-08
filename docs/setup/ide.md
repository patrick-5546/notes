# IDE

As a computer engineer, a significant portion of my time is spent programming. After using a variety of IDEs
I settled on Vim and VS Code, extensively configuring them to maximize my productivity.

## Showcase

This is what my VS Code configuration looked like when I was still using the [setup repository](https://github.com/patrick-5546/setup).
Currently my configuration looks mostly the same, but uses the Vim extension instead of the Neovim extension.

![IDE Demo](../assets/ide_demo.gif)

## Vim Keybindings

My IDEs of choice support Vim keybindings, which significantly reduces my mouse usage while programming.
After overcoming the steep learning curve, I was able to write code much faster.

Here are some Vim learning resources that I recommend:

- [Vim Tutorial](https://www.youtube.com/watch?v=IiwGbcd8S7I&t=1s)
- [Vim As Your Editor](https://www.youtube.com/watch?v=H3o4l4GVLW0&list=PLm323Lc7iSW_wuxqmKx_xxNtJC_hJbQ7R)
- [Mastering the Vim Language](https://www.youtube.com/watch?v=wlR5gYd6um0)
- [How to Do 90% of What Plugins Do (With Just Vim)](https://www.youtube.com/watch?v=XA2WjJbmmoM&t=734s)

I have extensively customized [my Vim configuration](https://github.com/patrick-5546/dotfiles/blob/main/dot_vimrc)
based on the following configurations:

- [amix/vimrc](https://github.com/amix/vimrc)
- [tylerlum/vim_configuration](https://github.com/tylerlum/vim_configuration)

## Vim

I use Vim to quickly modify a file from the terminal. I do not use any plugins, opting to use Neovim or VS Code when working on projects.
Vim is noticeably faster than Neovim with plugins or VS Code for large files.

Configuration file: [`.vimrc`](https://github.com/patrick-5546/dotfiles/blob/main/dot_vimrc)

## Neovim

Neovim is a fork of Vim which has powerful plugins that adds IDE features. I use it to edit projects in the CLI.
Since configuring these plugins is complicated and breaks all the time (because Neovim is still in rapid development),
I use the [LazyVim](https://github.com/LazyVim/LazyVim) distribution to manage all of this for me.
And for anything else that I want, LazyVim makes it easy to add my own configuration and plugins.

Configuration files: [`.config/nvim`](https://github.com/patrick-5546/dotfiles/tree/main/dot_config/nvim)

## VS Code

VS Code has great support for debugging, remote development, Git, most programming languages, and much more through extensions.
It is also extremely configurable, with its settings and keyboard shortcuts being able to be modified through a UI or JSON file.

To get Vim keybindings in VS Code I use the [Vim extension](https://marketplace.visualstudio.com/items?itemName=vscodevim.vim).
You can enable various features in its settings, which include some Vim extensions and using a `.vimrc`.

I use VS Code's built-in Settings Sync to sync my configuration, but have copied some of my configuration files to my dotfiles repository for your reference:

- [`reference_dotfiles/vscode/keybindings.json`](https://github.com/patrick-5546/dotfiles/blob/main/reference_dotfiles/vscode/keybindings.json)
- [`reference_dotfiles/vscode/settings.json`](https://github.com/patrick-5546/dotfiles/blob/main/reference_dotfiles/vscode/settings.json)

Resources:

- [VS Code user interface](https://code.visualstudio.com/docs/getstarted/userinterface)

### Extensions

In addition to the Vim extension and language and framework extension packs, I found the following extensions to be useful:

| Extension Name | Description |
| ----------- | ------------------------------------ |
| Edit csv | View and edit csv files with a table UI |
| Git History | View git log, file history, compare branches or commits |
| GitLens | See who committed each line of code and when they did it |
| Live Share Extension Pack | Real-time collaborative development |
| Path Intellisense | Autocomplete filenames |
| Peacock | Change workspace border color to be able to quickly identify workspaces |
| Remote Development | Support for development using WSL, SSH, and Docker |
| toggle semicolon | ++ctrl+semicolon++ to add or remove the semicolon at the end of a line |
| vscode-icons | Clean file icons for the file explorer |
| vscode-pdf | Display pdf file in VS Code |

### Quirks

Several quirks that I have noticed with my VS Code configuration:

- Undo and redo behavior is different in Vim and VS Code. Thus saving a file, making a change, then using ++u++ to undo will not bring the file back to its saved state
    - Workarounds: enable auto-saving or map ++u++ and ++ctrl+r++ to the VS Code implementation of undo and redo
- "Quick Fix" on Windows and Linux (++ctrl+comma++) is overridden by my toggle semicolon extension

### Software Infrastructure

VS Code has some amazing features that can be used to customize and automate your development environment for a project and share it with the project's developers.

#### Workspace Settings

[Workspace settings](https://code.visualstudio.com/docs/getstarted/settings#_workspace-settings)
customize the VS Code configurations of everyone who opens the workspace in VS Code.
Besides the settings.json file, you can add [launch configurations](https://code.visualstudio.com/docs/editor/debugging#_launch-configurations),
[recommended extensions](https://code.visualstudio.com/docs/editor/extension-marketplace#_workspace-recommended-extensions),
[tasks](https://code.visualstudio.com/docs/editor/tasks), and much more.
These files are stored in the `.vscode/` directory. Workspace settings override user settings.

Example workspace settings: [UBCSailbot/docs/.vscode](https://github.com/UBCSailbot/docs/tree/main/.vscode),
[UBCSailbot/sailbot_workspace/sailbot.code-workspace](https://github.com/UBCSailbot/sailbot_workspace/blob/main/sailbot.code-workspace).

#### Dev Container

[Dev container](https://code.visualstudio.com/docs/remote/containers)
wrap up your VS Code configuration with your dependencies in a [Docker](https://docs.docker.com/get-started/overview/) container.
These files are stored in the `.devcontainer/` directory.

Example dev container: [UBCSailbot/sailbot_workspace/.devcontainer](https://github.com/UBCSailbot/sailbot_workspace/tree/main/.devcontainer).

--8<-- "includes/abbreviations.md"
