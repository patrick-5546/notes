# Setup

My Windows laptop configuration as a computer engineering student.

## Philosophy

### Best of Both Worlds

Windows and Linux excel at different things:

- Windows has a better GUI and more powerful productivity apps
- Linux is better for programming

I use each OS to their advantage by running Windows on my personal device and using WSL to get a Linux environment on it.

??? info "WSL vs dual-boot"
    Dual-booting Windows and Linux is another way of running both OS's on a device, but WSL offers very similar performance in the majority of
    tasks while being much more convenient: WSL distributions can be started in a matter of seconds and can be used
    simultaneously with Windows apps. Especially with WSL adding the support for Linux GUI apps in Windows 11, there are a
    dwindling number of reasons to dual-boot. Some reasons include WSL's poor filesystem performance and the computer having little RAM (< 16GB).

### Minimize Mouse Usage

Every switch between using the mouse and keyboard takes time and energy, both of which I have little of. Thus, I use:

- Vim commands and VS Code shortcuts. See the [IDE](./ide.md) page to learn more.
- Keyboard shortcuts in Windows as much as possible.
See the [Windows Keyboard Shortcuts](../reference/shortcuts.md) page for a list of the shortcuts I frequently use.

### Same Experience Across Computers and Programs

To have the same experience on all the computers I use (personal, work, school, homelab), I:

1. Created a [dotfiles repository](https://github.com/patrick-5546/dotfiles) that contains my dotfiles and an installation script
    - Used [chezmoi](./cli/linux-cli.md#chezmoi) to manage these dotfiles across computers, OS's, and shells
2. Standardized keyboard shortcuts across programs
    - Largely based on my Vim and Microsoft Edge keyboard shortcuts
3. Standardized CLI configuration across shells
4. Wrote these notes so that I remember how everything works

--8<-- "includes/abbreviations.md"
