# :material-web: Material for MkDocs

This website was created using Material for MkDocs, a simple yet powerful framework for creating documentation.
All it requires is a Markdown file for every page, and a configuration file that connects everything together.
With Material for MkDocs providing [somewhat] customizable features, frontend, and deployment methods,
I can focus my time on the content of the site.

## Useful Documentation Pages

- [Search for icons](https://squidfunk.github.io/mkdocs-material/reference/icons-emojis/#search)
- [Types of collapsible blocks](https://squidfunk.github.io/mkdocs-material/reference/admonitions/#supported-types)
- [Keyboard keys syntax](https://facelessuser.github.io/pymdown-extensions/extensions/keys/#extendingmodifying-key-map-index)
- [Setup](https://squidfunk.github.io/mkdocs-material/setup/changing-the-colors/)
- [Reference](https://squidfunk.github.io/mkdocs-material/reference/)

## Setup

### Page Tree Example

Based on this site. Paths in the page tree are relative to `docs/`.

``` yaml
nav:
  - Home: index.md                      # Homepage, first tab
  - Setup:                              # Second tab
    - setup/index.md                    # Second tab homepage
    - Settings: setup/settings.md       # Second tab first page
  - Reference:                          # Third tab
    - Mkdocs: reference/docker.md.md    # Third tab first page (no third tab homepage)
```

### Plugins

!!! tip ""
    If you have no plugins entry in your config file yet, you'll likely also want to add the search plugin.
    MkDocs enables it by default if there is no plugins entry set.

- Automatic documentation generation using [mkdocstrings](https://mkdocstrings.github.io/)
- Page revision time using [mkdocs-git-revision-date-localized-plugin](https://github.com/timvink/mkdocs-git-revision-date-localized-plugin)

## Reference

<!-- TODO: link to reference/mkdocs.md raw on GitHub -->
Demonstrations of the features I use. View [this page raw](`reference/mkdocs.md`) for the Markdown syntax used.
View the documentation reference for what be in the configuration file to enable a feature.

### Collapsible blocks, code block formatting, embedding external files

??? quote "Click to toggle open/close"

    Syntax highlighting for inline code: Python's `#!python range()` function...

    ``` python title="Embed of docs/reference/mkdocs.md" linenums="1"
    --8<-- "docs/requirements.txt"
    ```

### Content tabs, icons, glossary

Markdown:

=== ":octicons-file-code-16: docs/example.md"

        1. Use the term (i.e. "WSL")
        2. Import glossary by adding to end of the file: --8<-- "includes/abbreviations.md"

=== ":octicons-file-code-16: includes/abbreviations.md"

    1. Define the term
    ```` markdown
    *[WSL]: Windows Subsystem for Linux
    ````

Result:

WSL is a term in the glossary.

### Table, keyboard keys

| Shortcut     | Description                          |
| ----------- | ------------------------------------ |
| ++alt++ + (++shift++) + ++tab++ | Navigate between windows |
| ++windows+ctrl++ + ++arrow-left++/++arrow-right++ | Navigate between virtual desktops |
| ++f11++ | Fullscreen |

### Task list, inline math equations

- [x] Result of task list
- [ ] Prove $e=mc^2$

## CI / CD Using GitHub Actions

### Lint

I use markdownlint to check for programmatic and stylistic errors in the application's Markdown files.

I configured the errors using a `.markdownlint.json` file in the project's root directory to support
the syntax of Material for MkDocs features.

??? quote "markdownlint configuration for this project"

    ``` json title=".markdownlint.json" linenums="1"
    --8<-- ".markdownlint.json"
    ```

??? quote "Lint workflow for this project"

    ``` yaml title=".github/workflows/lint.yml" linenums="1"
    --8<-- ".github/workflows/lint.yml"
    ```

markdownlint resources:

- [markdownlint rules reference](https://github.com/DavidAnson/markdownlint/blob/v0.24.0/doc/Rules.md)
- [markdownlint extension for VS Code](https://marketplace.visualstudio.com/items?itemName=DavidAnson.vscode-markdownlint)

### Deploy

The Materials for MkDocs documentation gives an example deploy workflow. I modified it slightly
to properly support page revision times using [mkdocs-git-revision-date-localized-plugin](./mkdocs.md#plugins).

??? quote "Deploy workflow for this project"

    ``` yaml title=".github/workflows/deploy.yml" linenums="1"
    --8<-- ".github/workflows/deploy.yml"
    ```

--8<-- "includes/abbreviations.md"