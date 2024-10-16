# Krystal Vale Package

This repository contains a [Vale-compatible](https://vale.sh/) implementation of what we hope to turn into a Krystal style guide.

## Getting Started

### I have a `vale.ini` already

To get started, add the package to your configuration file (as shown below) and then run `vale sync`.

```ini
StylesPath = styles # Use your normal style path here.
Packages = https://github.com/krystal/vale-package/releases/latest/download/vale.zip
```

### Add Vale to a project

Create a `.vale.ini` at the project's root:
```ini
StylesPath = vale-styles  # Location of styles directory
MinAlertLevel = suggestion # Options: suggestion, warning, error
Packages = https://github.com/krystal/vale-package/releases/latest/download/vale.zip

[*.md]  # Apply to markdown files
BasedOnStyles = Krystal
```

See [Vale's documentation on packages](https://vale.sh/docs/topics/packages/) for more information.

### Setup whilst the Vale package is a private repository

Before we make this Vale package public, it cannot be downloaded via `vale sync` with the above config. We'll use the GitHub CLI to simplify grabbing an auth token. You may generate a `PAT` and use that instead if you wish.

> [!TIP]
> Install the [GitHub CLI](https://cli.github.com/) and authenticate it first.

```shell
curl -L -H "Authorization: token $(gh auth token)" \
     -o vale-package-0.1.0.zip \
     https://github.com/krystal/vale-package/archive/refs/tags/v0.1.0.zip
```

Add `vale-package.zip` to `.gitignore`.

Create `.vale.ini`.

```ini
StylesPath = vale-styles  # Location of styles directory
MinAlertLevel = suggestion # Options: suggestion, warning, error
Packages = vale-package-0.1.0.zip

[*.md]  # Apply to markdown files
BasedOnStyles = Krystal
```

Run `vale sync`.
