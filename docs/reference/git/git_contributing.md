# :material-rocket-launch: Contributing to a Git Repository

For a walkthrough of the contribution process, read [First Contributions](https://github.com/firstcontributions/first-contributions/blob/master/README.md).

!!! note "Comments on the First Contributions walkthrough"
    - If you have access to the repository, there is no need to fork it; clone and work on the repository itself

## Goals

- Main branch only contains working code
- Collaborate with others effectively (i.e., code reviews)
- Clear, progressive development process

## Issues

- Bug: Describe issue, steps to reproduce, expected behavior, screenshots, additional context
- Feature: Give context, describe solution, describe alternatives, additional context
- Link to relevant code, projects, labels, milestones, etc.

## Commits

- Make a commit for each unit change, giving it a descriptive name
    - For example: "added `<function_name>` function", "updated tests to match"
- At the end of a session `git push`, to update the remote repository with your changes

## Pull requests

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

## Updating your local repository

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
    - Local branches tracking a remote that has been prunes are identified as gone in the output of `git branch -vv`
        - Delete these branches with `git branch -D <branch1> <branch2> ...`
    - Reference: [Cleaning up old remote git branches](https://stackoverflow.com/questions/3184555/cleaning-up-old-remote-git-branches)

## GitHub-specific best practices

- Labels: [GitHub labels best practices](https://medium.com/@dave_lunny/sane-github-labels-c5d2e6004b63)
- Milestones and projects: [Milestones vs. projects](https://stackoverflow.com/a/39701381)
- Discussions: gather feedback and ideas from non-code collaborators
    - [Best practices for community conversations](https://docs.github.com/en/discussions/guides/best-practices-for-community-conversations-on-github)
- Actions: automate, customize, and execute software development workflows
    - [Actions documentation](https://docs.github.com/en/actions)
    - [GitHub Marketplace - Actions](https://github.com/marketplace?type=actions)
    - [Explanation of this project's workflows](../mkdocs.md#ci-cd-using-github-actions)
    - [Encrypted secrets documentation](https://docs.github.com/en/actions/security-guides/encrypted-secrets)
- Wiki: host very basic documentation,
[GitHub Flavored Markdown](https://docs.github.com/en/github/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax) only
    - [Advanced Formatting in GitHub Markdown](https://gist.github.com/apaskulin/1ad686e42c7165cb9c22f9fe1e389558)
    - [Render a code snippet in an issue](https://docs.github.com/en/github/writing-on-github/working-with-advanced-formatting/creating-a-permanent-link-to-a-code-snippet#linking-to-code)
- [Choosing the right open source license](https://choosealicense.com/)
