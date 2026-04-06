# ESDIS Cloud Data Services Governance Model

This is a documentation site to support development and maintenance of data
services within the ESDIS Project.

The documentation is published as a GitHub Pages
[website](https://nasa.github.io/esdis-services-governance-model/).

It is under active development through collaboration of the ESDIS Transformation
Train.

## Installation

### Quarto

Install Quarto by downloading the installer for your platform from
[quarto.org/docs/get-started](https://quarto.org/docs/get-started/), or via a
package manager:

- **macOS (Homebrew):** `brew install --cask quarto`
- **Linux:** Download the `.deb` or `.rpm` package from the Quarto website
- **Windows:** Download the `.msi` installer from the Quarto website

Verify the installation with `quarto check`.

## Development

To preview the site locally:

```bash
quarto preview
```

## CI/CD

CI/CD is configured to publish the rendered documentation to GitHub pages:

* `.github/workflows/pr-preview.yml` - builds the documentation website from the
  branch under review, providing a link to the outputs from that build.
* `.github/workflows/publish.yml` - Publishes a new version of the documentation
  when a PR is merged into the `main` branch.

## pre-commit

This repository uses [pre-commit](https://pre-commit.com/) to enable pre-commit
checking the repository for some coding standard best practices. These include:

* Removing trailing whitespaces.
* Removing blank lines at the end of a file.
* JSON and YAML files have valid formats.
* [ruff](https://github.com/astral-sh/ruff) Python linting checks.
* [black](https://black.readthedocs.io/en/stable/index.html) Python code
  formatting checks.

To enable these checks:

```bash
# Install pre-commit Python package as part of test requirements:
pip install pre-commit

# Install the git hook scripts:
pre-commit install

# (Optional) Run against all files:
pre-commit run --all-files
```

When you try to make a new commit locally, `pre-commit` will automatically run.
If any of the hooks detect non-compliance (e.g., trailing whitespace), that
hook will state it failed, and also try to fix the issue. You will need to
review and `git add` the changes before you can make a commit.

[pre-commit.ci](pre-commit.ci) is configured such that these same hooks will be
automatically run for every pull request.
