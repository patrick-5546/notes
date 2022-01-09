# :material-remote-desktop: SSH

## Setup SSH Keys

SSH key-based authentication allows you SSH into remote machines without a password.

Guide: [Setup SSH keys](https://linuxize.com/post/how-to-set-up-ssh-keys-on-ubuntu-20-04/)

!!! note "Notes on the guide"
    - Although the guide is for Ubuntu 20.04, it should work for most Linux distributions
        - It also works in PowerShell, using the given alternative to `ssh-copy-id`

## Other Resources

- [`ssh` command guide](https://linuxize.com/post/ssh-command-in-linux/)
- [Specify the starting directory for a SSH session](https://docs.microsoft.com/en-us/windows/terminal/tutorials/ssh#specify-starting-directory)
- [Setup SSH keys on Synology DSM 6](https://stamler.ca/enable-passwordless-ssh-on-synology-dsm6/)

    ??? note "Notes on the Synology guide"
        The command to restart the sshd service will likely not work.
        In this case, telnet in to restart the service

        ``` sh
        sudo synoservicectl --restart sshd  # restarting the sshd service may fail
        telnet -l <username> <host_name>  # telnet into the NAS
        sudo synoservicectl --start sshd  # start the sshd service
        ```
