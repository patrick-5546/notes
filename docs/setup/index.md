# Setup

My Windows laptop configuration as a computer engineering student.

## Philosophy

### Best of Both Worlds

Windows and Linux excel at different things:

- Windows has a better GUI and more powerful productivity apps
- Linux is better for programming

I use each OS to their advantage by running Windows on my personal device and using WSL to get a Linux environment on it.

??? info "WSL vs dual-boot"
    Dual-booting Windows and Linux was popular in the past, but WSL offers very similar performance in the majority of
    tasks while being much more convenient: WSL distributions can be started in a matter of seconds and can be used
    simultaneously with Windows apps. Especially with WSL adding the support for Linux GUI apps in Windows 11, there are a
    dwindling number of reasons to dual-boot. One such reason is that the computer has little RAM (< 16GB).

### Minimize Mouse Usage

Every switch between using the mouse and keyboard takes time and energy, both of which I have little of. Thus, I use:

- Vim commands to write text/code without the need for a mouse. See the [IDE](./ide.md) page to learn more.
- Keyboard shortcuts in Windows as much as possible.

### Same Keyboard Shortcuts Across Programs

To minimize the number of keyboard shortcuts I need to memorize, I configure the programs I use to
have the same keyboard shortcuts.

### Consistent Across Computers

To have the same experience on all the computers I use (personal, work, research, homelab), I:

1. Created a [setup repository](https://github.com/patrick-5546/setup) that contains all my configuration files and a script that installs my Linux packages and Zsh plugins
2. Wrote these notes so that I remember how everything works

--8<-- "includes/abbreviations.md"
