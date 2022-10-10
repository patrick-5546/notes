# :material-git: Git Commands

## File Specifiers

| Specifier | Description |
| --------- | ----------- |
| `.` | Everything new/modified in current directory |
| `-u` | Files in the remote repository that were modified in the current directory |
| `<path/to/file_name>` | Specific file |

- Use `git status` to check if the command had the desired outcome

## Commands

Useful Git commands that build on top of the add, commit, and push workflow.

### cherry-pick

Cherry picking is useful but not always best practice. It can create duplicate commits, and merging would be preferred
in most scenarios. To avoid duplicate commits I do not merge the branch with the commit(s) I am cherry picking
into the main branch. I use cherry picking to clean up a branch's commit history when changing which branch its PR
is merging into.

| Command | Description |
| --------- | ----------- |
| `git cherry-pick <commit hash>` | Add commit to the current branch |
| `git cherry-pick <commit A hash>^..<commit B hash>` | Add commits from A to B inclusive, where A is older than B, to the current branch |

### log

| Command | Description |
| --------- | ----------- |
| `git log` | Check the commit history of the current branch |

### mv

Sometimes after moving a file and making changes to it Git isn't able to detect that the file was moved.
Instead, it thinks the file was deleted and a new one was created, which wipes its file history.
To preserve file history, commit the move before making any changes to the file.
This is most easily done with the `git mv` command.

| Command | Description |
| --------- | ----------- |
| `git mv <src> <dest or dest directory>` | Like `mv` but stages the move |

### restore

Undo uncommitted changes.

| Command | Description |
| --------- | ----------- |
| `git restore <file specifier>` | Revert files to their state on the remote repository (delete local changes) |
| `git restore --staged <file specifier>` | Unstage/un-add files |

### reset

Undo committed (but not pushed) changes.

| Command | Description |
| --------- | ----------- |
| `git reset HEAD~1` | Unstage the changes made in last commit, but do not modify the files |
| `git reset --hard HEAD~5` | Undo the changes made in the last 5 commits |

### rm

Remove files

| Command | Description |
| --------- | ----------- |
| `git rm <file specifier>` | Remove files from Git and delete them |
| `git rm --cached <file specifier>` | Remove files from Git but do not delete them |

### stash

Stash uncommitted changes so that you can pull or switch branches.

| Command | Description |
| --------- | ----------- |
| `git stash` | Stash changes |
| `git stash pop` | Restore changes |

## Advanced Features

### Rebase

Rebase is a powerful, but if used incorrectly it can permanently mess up your Git history.
Always remember to check the commit history with `git log` to ensure that it is what you want
before force pushing it to the remote repository with `git push -f`.

#### Standard Mode

> From [git-rebase Documentation - Git](https://git-scm.com/docs/git-rebase)

Assume the following history exists and the current branch is "topic":

```
          A---B---C topic
         /
    D---E---F---G main
```

From this point, the result of either of the following commands:

```
git rebase main
git rebase main topic
```

would be:

```
                  A'--B'--C' topic
                 /
    D---E---F---G main
```

If the local main branch is outdated with the remote main branch, use

```
git rebase origin/main
```

to rebase the current branch onto the remote main branch.

#### Interactive Mode

> From [git rebase | Atlassian Git Tutorial](https://www.atlassian.com/git/tutorials/rewriting-history/git-rebase#:~:text=What%20is%20git%20rebase%3F,of%20a%20feature%20branching%20workflow.)

Running git rebase with the `-i` flag begins an interactive rebasing session.
Instead of blindly moving all of the commits to the new base, interactive rebasing gives you the opportunity to alter individual commits in the process.
This lets you clean up history by removing, splitting, and altering an existing series of commits.

```
git rebase -i main
```

rebases the current branch onto main but uses an interactive rebasing session.
This opens an editor where you can enter commands for each commit to be rebased.
These commands determine how individual commits will be transferred to the new base.
You can also reorder the commit listing to change the order of the commits themselves.
Once you've specified commands for each commit in the rebase, Git will begin playing back commits applying the rebase commands.

??? info "Interactive Rebasing Edit Commands"

    ```
    pick 2231360 some old commit
    pick ee2adc2 Adds new feature

    # Rebase 2cf755d..ee2adc2 onto 2cf755d (9 commands)
    #
    # Commands:
    # p, pick = use commit
    # r, reword = use commit, but edit the commit message
    # e, edit = use commit, but stop for amending
    # s, squash = use commit, but meld into previous commit
    # f, fixup = like "squash", but discard this commit's log message
    # x, exec = run command (the rest of the line) using shell
    # d, drop = remove commit
    ```

#### Resolving Conflicts

> From [git-rebase Documentation - Git](https://git-scm.com/docs/git-rebase)

In case of conflict, git rebase will stop at the first problematic commit and leave conflict markers in the tree.
You can use git diff to locate the markers (<<<<<<) and make edits to resolve the conflict.
For each file you edit, you need to tell Git that the conflict has been resolved, typically this would be done with

```
git add <filename>
```

After resolving the conflict manually and updating the index with the desired resolution, you can continue the rebasing process with

```
git rebase --continue
```

Alternatively, you can undo the git rebase with

```
git rebase --abort
```
### Remote Repositories

There may be cases where you want to keep mirrors of your repository.

- The original remote repository is given the identifier `origin` by default

| Command | Description |
| --------- | ----------- |
| `git remote add <repo name> <repo base url>.git` | Add a remote repository and give it the identifier `<repo name>` |
| `git push <repo name> --all` | Push all branches to a remote repository |
| `git remote -v` | List remote repositories |
| `git remote remove <repo name>` | Remove a remote repository |

### Submodules

Add a Git repository inside another Git repository, usually to serve as a dependency.

| Command | Description |
| --------- | ----------- |
| `git submodule add <repo base url>.git` | Add a repository as a submodule of the current repository |
| `git diff --submodule` | Better diff for submodules from the parent repository |
| `git submodule update --remote --merge` | Update submodules to their latest remote commits |
| `git submodule update --init --recursive` | Recursively initialize and update submodules to the commits in the remote parent repository |
| `git clone --recurse-submodules <repo base url>.git` | Clone a repository and recursively initialize all its submodules |

Resources:

- [Submodule chapter in the Git book](https://git-scm.com/book/en/v2/Git-Tools-Submodules)
- [Create a submodule that tracks a specific branch](https://stackoverflow.com/questions/9189575/git-submodule-tracking-latest/9189815#9189815)
- [Properly remove a submodule](https://stackoverflow.com/a/1260982)

### Tags

Tag a commit. I usually create tags as part of [publishing a release on GitHub](https://docs.github.com/en/repositories/releasing-projects-on-github/managing-releases-in-a-repository),
but the CLI commands may come in handy if you want to delete a release and its associated tag.

| Command | Description |
| --------- | ----------- |
| `git tag -d <tag name>` | Delete local tag |
| `git tag -a <tag name> -m "<description>"` | Create an annotated tag for the current commit |
| `git push --tags` | Push tags to the remote repository |
| `git show <tag name>` | See tag information |
| `git checkout <tag name>` | Checkout to the commit that a tag points to |

Resources:

- [Tagging - Git](https://git-scm.com/book/en/v2/Git-Basics-Tagging)

### Work Trees

Git work trees allow you to have allow you to develop multiple branches of a repository at the same time.

| Command | Description |
| --------- | ----------- |
| `git clone --bare <repo base url>.git` | Clone a repository as a bare repository |
| `git worktree add <directory>` | Create a work tree at the specified location, checking out to the branch of the same name or creating one if it does not exist |
| `git worktree add -b <branch name> <directory>` | Same as above, but needed if `<branch name>` contains forward slashes |
| `git worktree list` | List all work trees |
| `git worktree remove <directory>` | Remove a worktree at the specified location |

Resources:

- [Git's Best And Most Unknown Feature](https://www.youtube.com/watch?v=2uEqYw-N8uE)
