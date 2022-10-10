# :material-git: Git Commands

Useful Git commands that build on top of the add, commit, and push workflow.

!!! info "File Specifiers"

    File specifiers are used in commands like `add`, [`restore`](#restore), and [`rm`](#rm) to specify which file(s) to apply to.

    | Specifier | Description |
    | --------- | ----------- |
    | `-u` | Files in the remote repository that were **modified** in the current directory |
    | `.` | Everything **new or modified** in current directory |
    | `<path/to/directory>` | Everything **new or modified** in a directory |
    | `<path/to/file>` | **New or modified** file |

    Use `git status` to check if the command had the desired outcome.

## cherry-pick

Cherry picking is useful but not always best practice. It can create duplicate commits, and merging would be preferred
in most scenarios. To avoid duplicate commits I do not merge the branch with the commit(s) I am cherry picking
into the main branch. I use cherry picking to clean up a branch's commit history when changing which branch its PR
is merging into.

| Command | Description |
| --------- | ----------- |
| `git cherry-pick <commit hash>` | Add commit to the current branch |
| `git cherry-pick <commit A hash>^..<commit B hash>` | Add commits from A to B inclusive, where A is older than B, to the current branch |

## log

| Command | Description |
| --------- | ----------- |
| `git log` | Check the commit history of the current branch |

## mv

Sometimes after moving a file and making changes to it Git isn't able to detect that the file was moved.
Instead, it thinks the file was deleted and a new one was created, which wipes its file history.
To preserve file history, commit the move before making any changes to the file.
This is most easily done with the `git mv` command.

| Command | Description |
| --------- | ----------- |
| `git mv <src> <dest or dest directory>` | Like `mv` but stages the move |

## reset

Undo committed (but not pushed) changes.

| Command | Description |
| --------- | ----------- |
| `git reset HEAD~1` | Unstage the changes made in last commit, but do not modify the files |
| `git reset --hard HEAD~5` | Undo the changes made in the last 5 commits |

## restore

Undo uncommitted changes.

| Command | Description |
| --------- | ----------- |
| `git restore <file specifier>` | Revert files to their state on the remote repository (delete local changes) |
| `git restore --staged <file specifier>` | Unstage/un-add files |

## rm

Remove files

| Command | Description |
| --------- | ----------- |
| `git rm <file specifier>` | Remove files from Git and delete them |
| `git rm --cached <file specifier>` | Remove files from Git but do not delete them |

## stash

Stash uncommitted changes so that you can pull or switch branches.

| Command | Description |
| --------- | ----------- |
| `git stash` | Stash changes |
| `git stash pop` | Restore changes |
