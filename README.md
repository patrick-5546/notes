# notes

Website for my notes on various programming-related topics.

## Setup

1. Clone repository

    ```
    git clone https://github.com/patrick-5546/notes.git
    ```

2. Install dependencies

    ```
   pip install -r docs/requirements.txt
   ```

    - Can do this in a [Python virtual environment](https://patrick-5546.github.io/notes/reference/python/#virtual-environments)

3. Manually install [social plugin OS dependencies](https://squidfunk.github.io/mkdocs-material/setup/setting-up-social-cards/#dependencies)

## Run

### VS Code

1. `CTRL+P` to open Quick Open
2. Run a launch configuration
    - "debug Run Application" runs `mkdocs serve`
    - "debug Launch Application" runs `mkdocs serve` and opens the application in a new Microsoft Edge window

### Command Line

1. `mkdocs serve`

## Versioning

1. Pull requests to main are deployed to `rolling`: `mike deploy --push rolling`
2. Releases are deployed to `<x.x>`, which is aliased to `latest`: `mike deploy --push --update-aliases <x.x> latest`
    - Set this as default version: `mike set-default --push latest`
        - Only have to do this once as setting alias as default then updating alias
3. Consider deploying pull requests to `<branch-name>`: `mike deploy --push devel-<branch-name>`
