# chapel-vscode extension

## Features

- Intellisense
  - GotoDefinition: jump to a symbols definition
  - Hover: hover over a symbol to view its signature and documentation
  - Code Completion: suggest completion for symbols in the current file
  - Symbol List: see all symbols for a file
  - Errors/Warning: see Chapel errors and warnings
- Linting
  - see Chapel linter warnings on potential errors and style suggestions
- Snippets
- Syntax Highlighting

## Setup

After installing the extension, follow these steps to make sure VSCode is setup to use the extension.

### From an existing Chapel build

The extension can auto-detect your `CHPL_HOME`, just open a Chapel file. The extension will prompt you to select an existing Chapel install to configure your editor. If you don't see your value of `CHPL_HOME` or don't know the right one, run `chpl --print-chpl-home` to get the right value. If the automatic installation fails, you can explicitly set your `CHPL_HOME` in your VSCode settings.json as `"chapel.CHPL_HOME": "/path/to/your/chapel/home"`.

The extension can also auto-build the Chapel language tools and will prompt you to do so if they are missing. If you prefer to build them manually, run the following: `(export CHPL_HOME=/path/to/your/chapel/home && cd $CHPL_HOME && make chpl-language-server && make chplcheck)`

### Without an existing Chapel build

1. Obtain a copy of latest Chapel source release from <https://chapel-lang.org/download.html>
2. After downloading the tar, extract the source tree with `tar xzf chapel-VERSION.tar.gz`
3. After unpacking the tar, you can treat this as your `CHPL_HOME` (`"/path/to/unpacked/source/chapel-VERSION"`) and follow the steps for an existing Chapel build.

## Linter options

Individual linter rules in the Chapel linter, `chplcheck`, can be turned on or off. This is done by adding arguments to your VSCode settings. For example, the following turns on the NestedCoforalls and UnusedFormal rules.

```json
"chapel.chplcheck.args": [
  "--enable-rule", "NestedCoforalls", "--enable-rule", "UnusedFormal"
],
```
