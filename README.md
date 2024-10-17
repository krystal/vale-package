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
