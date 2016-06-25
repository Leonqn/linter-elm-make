# linter-elm-make

Lint your Elm files in Atom with [linter](https://github.com/atom-community/linter) and `elm-make`.

![lint-on-fly](https://github.com/mybuddymichael/linter-elm-make/blob/master/images/lint-on-fly.gif?raw=true)

## Installation

1. [Install `elm`](http://elm-lang.org/install).
1. `$ apm install linter`
1. `$ apm install language-elm`
1. `$ apm install linter-elm-make`
1. `$ which elm-make` and set that as your executable path in this installed package's configuration.

## Configuration

#### Lint On The Fly
By default, linting is only done after saving the file.  If you want to lint while typing, turn on the `Lint On The Fly` option in the package settings.  Also make sure that the `Lint As You Type` option is enabled in the [linter](https://github.com/atom-community/linter) package settings.

#### Always Compile Main
If enabled, the main file(s) will always be compiled instead of the active file.  The main file can be set using `Linter Elm Make: Set Main Path`.  If not set, the linter will look for `Main.elm` files in the source directories.  Take note that if this is enabled, modules unreachable from the main modules will not be linted.  Disabled by default.

#### Report Warnings
Show `elm-make` warnings.  Enabled by default.

## Quick Fixes

#### `Linter Elm Make: Quick Fix`
Move your cursor to a problematic text range and invoke this command to show the possible fixes. Select a fix from the list to apply it to your code.

![quick-fix](https://github.com/mybuddymichael/linter-elm-make/blob/master/images/quick-fix.png?raw=true)

#### `Linter Elm Make: Quick Fix All`
Fixes all issues in the active text editor in one go. If there is more than one fix for an issue, it will choose the first from the list.

You may also add something like this in your `keymap.cson`:

```
'atom-text-editor:not([mini])[data-grammar^="source elm"]':
  'f6': 'linter-elm-make:quick-fix'
  'shift-f6': 'linter-elm-make:quick-fix-all'

'.linter-elm-make atom-text-editor[mini]':
    'f6': 'core:confirm'
```

## Other Useful Commands

#### `Linter Elm Make: Toggle Lint On The Fly`

#### `Linter Elm Make: Toggle Always Compile Main`

#### `Linter Elm Make: Clear Project Build Artifacts`
Deletes the `*.elmi` and `*.elmo` files in your project's build artifacts directory (e.g. elm-stuff/build-artifacts/0.17.0/user/project/1.0.0).  This is useful after toggling `Lint On The Fly` and/or `Always Compile Main` to prevent confusing lint results.

## Prior Art

The boilerplate code here is repurposed from [linter-hlint](https://github.com/AtomLinter/linter-hlint). Much thanks to its [contributors](https://github.com/AtomLinter/linter-hlint/graphs/contributors).
