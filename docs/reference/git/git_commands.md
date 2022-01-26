# :material-git: Git Commands

!!! info "File specifiers"

    | Specifier | Description |
    | --------- | ----------- |
    | `.` | Everything new/modified in current directory |
    | `-u` | Files in the remote repository that were modified in the current directory |
    | `<path/to/file_name>` | Specific file |

    - Use `git status` to check if the command had the desired outcome

## Restore

Undo uncommitted changes.

| Command | Description |
| --------- | ----------- |
| `git restore <file_specifier>` | Revert files to their state on the remote repository (delete local changes) |
| `git restore --staged <file_specifier>` | Unstage/un-add files |

## Reset

Undo committed (but not pushed) changes.

| Command | Description |
| --------- | ----------- |
| `git log` | Check the commit history of the current branch |
| `git reset HEAD~1` | Unstage the changes made in last commit, but do not modify the files |
| `git reset --hard HEAD~5` | Undo the changes made in the last 5 commits |

## Rm

Remove files

| Command | Description |
| --------- | ----------- |
| `git rm <file_specifier>` | Remove files from Git and delete them |
| `git rm --cached <file_specifier>` | Remove files from Git but do not delete them |

## Stash

Stash uncommitted changes so that you can pull or switch branches.

| Command | Description |
| --------- | ----------- |
| `git stash` | Stash changes |
| `git stash pop` | Restore changes |

## Tags

Tag a commit (i.e., release version, milestone).

| Command | Description |
| --------- | ----------- |
| `git tag -a <tag_name> -m "<description>"` | Create an annotated tag for the current commit |
| `git push --tags` | Push tags to the remote repository |
| `git show <tag_name>` | See tag information |
| `git checkout <tag_name>` | Checkout to the commit that a tag points to |
| `git tag -d <tag_name>` | Delete local tag |
| `git push origin --delete <tag_name>` | Delete tag from the remote repository |

Resources:

- [Tagging chapter in the Git book](https://git-scm.com/book/en/v2/Git-Basics-Tagging)

## Manage remote repositories

There may be cases where you want to keep mirrors of your repository.

- The original remote repository is given the identifier `origin` by default

| Command | Description |
| --------- | ----------- |
| `git remote add <repo_name> <repository_base_url>` | Add a remote repository and give it the identifier `<repo_name>` |
| `git push <repo_name> --all` | Push all branches to a remote repository |
| `git remote -v` | List remote repositories |
| `git remote remove <repo_name>` | Remove a remote repository |

## Submodules

Manage a Git repository from inside another Git repository.

| Command | Description |
| --------- | ----------- |
| `git submodule add <repository_base_url>` | Add a repository as a submodule of the current repository |
| `git diff --submodule` | Better diff for submodules from the parent repository |
| `git submodule update --remote --merge` | Update submodules to their latest remote commmits |
| `git submodule update --init --recursive` | Recursively initialize and update submodules to the commits in the remote parent repository |
| `git clone --recurse-submodules <repo_base_url>` | Clone a repository and recursively initialize all its submodules |

Resources:

- [Submodule chapter in the Git book](https://git-scm.com/book/en/v2/Git-Tools-Submodules)
- [Create a submodule that tracks a specific branch](https://stackoverflow.com/questions/9189575/git-submodule-tracking-latest/9189815#9189815)
- [Properly remove a submodule](https://stackoverflow.com/a/1260982)

## Oh My Zsh Git plugin aliases

The [Zsh Git plugin](https://github.com/ohmyzsh/ohmyzsh/tree/master/plugins/git) provides many aliases;
I have listed the ones I regularly use below.

``` sh
ga='git add'
gb='git branch'
gbD='git branch -D'
gco='git checkout'
gcb='git checkout -b'
gcm='git checkout $(git_main_branch)'
gcl='git clone --recurse-submodules'
gcmsg='git commit -m'
gd='git diff'
gdca='git diff --cached'
gmom='git merge origin/$(git_main_branch)'
gl='git pull'
gp='git push'
gpsup='git push --set-upstream origin $(git_current_branch)'
gra='git remote add'
grv='git remote -v'
grrm='git remote remove'
grh='git reset'
grhh='git reset --hard'
grs='git restore'
grst='git restore --staged'
grm='git rm'
grmc='git rm --cached'
gst='git status'
gsu='git submodule update'
```
