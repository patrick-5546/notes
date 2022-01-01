# :material-rocket-launch: Contributing to a Git Repository

## Read [First Contributions](https://github.com/firstcontributions/first-contributions/blob/master/README.md)

## Additonal Notes

### Goals

- Main branch only contains working code
- Collaborate with others effectively (i.e., code reviews)
- Clear, progressive development process

### Issues

- Bug: Describe issue, steps to reproduce, expected behavior, screenshots, additional context
- Feature: Give context, describe solution, describe alternatives, additional context
- Link to relevant code, projects, labels, milestones, etc.

### Commits

- Make a commit for each unit change, giving it a descripting name
    - For example: "added <function_name> function", "updated tests to match"
- At the end of a session `git push`, to update the remote repository with your changes

### Pull requests

Compared to committing directly to the main branch, pull requests can be used to ensure that the code in the main branch is clear and correct through:

- Continuous integration: automated linting and testing
- Code reviews: getting someone to read over and test your code

Creating a pull request:

- Describe changes, expected behavior, and how to verify
- Link pull request to the issue it resolves: [linking a pull request to an issue](https://docs.github.com/en/issues/tracking-your-work-with-issues/linking-a-pull-request-to-an-issue)
- Can create as a draft if incomplete, which disables merging
    - New commits to the branch will be automatically added to the pull request
- Add reviewers to test the pull request
- Once the pull request is ready to merge into the main branch, I recommend the "Squash and Merge" merge method to keep the main branch commit history clear and concise,
or "Rebase and Merge" for hotfixes and one off commits
    - Learn more about GitHub merge types and best practices [here](https://rietta.com/blog/github-merge-types/)

### Updating your local repository

``` title="Update the current local branch and the remote tracking branches for all other branches"
git pull --rebase
```

- [Why use `--rebase`?](https://stackoverflow.com/a/4675513)
- Make `git pull` rebase by default with `git config --global pull.rebase true`

``` title="Update current local branch with commits in the main local branch"
git merge origin/main
```

``` title="Delete remote tracking branches that were deleted from the remote repository"
git remote prune origin
```

- Make `git pull` or `git fetch` prune by default with `git config --global fetch.prune true`
- Local branches tracking a remote that is gone are identified as gone when using `git branch -vv`
    - Delete a local branch with `git branch -D <branch_name>`
- Learn more: [Cleaning up old remote git branches](https://stackoverflow.com/questions/3184555/cleaning-up-old-remote-git-branches)
