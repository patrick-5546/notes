# :material-web: Mkdocs

## Useful Documentation Pages

- [Search for icons](https://squidfunk.github.io/mkdocs-material/reference/icons-emojis/#search)
- [Types of collapsible blocks](https://squidfunk.github.io/mkdocs-material/reference/admonitions/#supported-types)
- [Keyboard keys syntax](https://facelessuser.github.io/pymdown-extensions/extensions/keys/#extendingmodifying-key-map-index)
- [Setup (configuration file)](https://squidfunk.github.io/mkdocs-material/setup/changing-the-colors/)
- [Reference](https://squidfunk.github.io/mkdocs-material/reference/)

## Reference Examples

<!-- TODO: link to reference/mkdocs.md raw on GitHub -->
Demonstrations of the features I regularly use. View this file (`reference/mkdocs.md`) raw for the syntax.
View the documentation to see which extensions need to be included in the configuration file (`mkdocs.yml`)

### Collapsible blocks, code block formatting, embedding external files

??? quote "Result of collapsible blocks, code block formatting, and embedding external files"

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

### Table, keyboard shortcuts

Result:

| Shortcut     | Description                          |
| ----------- | ------------------------------------ |
| ++alt++ + (++shift++) + ++tab++ | Navigate between windows |
| ++windows+ctrl++ + ++arrow-left++/++arrow-right++ | Navigate between virtual desktops |
| ++f11++ | Fullscreen |

### Task list, inline math equations (MathJax)

- [x] Result of task list
- [ ] Prove $e=mc^2$

## Project Layout

    mkdocs.yml    # The configuration file.
    docs/
        index.md  # The documentation homepage.
        ...       # Other markdown pages, images and other files.
    includes/
        abbreviations.md  # The glossary, defining terms used across the docs.

### Page tree

``` yaml
theme:
  name: material
  features:
    - navigation.tabs

nav:
  - Home: index.md                      # Homepage, first tab
  - Setup:                              # Second tab
    - setup/index.md                    # Second tab homepage
    - Settings: setup/settings.md       # Second tab first page
  - Reference:                          # Third tab
    - Mkdocs: reference/docker.md.md    # Third tab first page (no third tab homepage)
```

## Extras

### Markdown Lint

1. Use VS Code's [markdownlint extension](https://marketplace.visualstudio.com/items?itemName=DavidAnson.vscode-markdownlint)
    1. If not using VS Code, can also [install the tool](https://github.com/markdownlint/markdownlint)
2. Modify/exclude rules in `.markdownlint.json` in the root directory
    1. [markdownlint rules](https://github.com/DavidAnson/markdownlint/blob/v0.24.0/doc/Rules.md)

??? quote ".markdownlint.json file for this project"

    ``` json linenums="1"
    --8<-- ".markdownlint.json"
    ```

### Github actions

#### Lint

#### Deploy to Github Pages

--8<-- "includes/abbreviations.md"
