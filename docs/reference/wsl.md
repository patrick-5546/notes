# :material-microsoft-windows: WSL

Importing and exporting WSL distributions

```
wsl --export Ubuntu ubuntu.tar
wsl --import Ubuntu2 .\Ubuntu2 ubuntu.tar
```

Add the following to `/etc/wsl.conf`

``` yaml
[user]
default=<username>
```

then `wsl -t Ubuntu`

Remove files for a distribution

```
wsl --unregister Ubuntu2
```

Signing in to Git using the windows credential manager

```
git config --global credential.helper "/mnt/c/Program\ Files/Git/mingw64/libexec/git-core/git-credential-manager-core.exe"
```

```
wsl -l -v
wsl -t Ubuntu
```

--8<-- "includes/abbreviations.md"
