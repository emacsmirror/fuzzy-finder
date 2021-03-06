[![MELPA](https://melpa.org/packages/fuzzy-finder-badge.svg)](https://melpa.org/#/fuzzy-finder)
[![MELPA Stable](https://stable.melpa.org/packages/fuzzy-finder-badge.svg)](https://stable.melpa.org/#/fuzzy-finder)


fuzzy-finder.el
===============

Fuzzy Finder App Integration for Emacs

![cap](cap.gif)


Overview
--------

The `fuzzy-finder` command starts a fuzzy finder process and calls a function
on the selected items.
By default it visits selected files.

There are a number of applications which can be used with `fuzzy-finder`
such as [fzf][] (default), [peco], and [selecta][].



Compared to Other Selector Frameworks (like Helm, Ivy...)
---------------------------------------------------------

There are several Emacs frameworks for selecting items that purely (or mostly)
implemented in Emacs-Lisp.
For most cases these frameworks are better suited than this package.
For example, when selecting command for `M-x`, opening files from the recentf
list, or looking for a function's help.

However, this package has one big advantage which these frameworks do not
provide: you can start querying and selecting items *before* the input list has
been completed.
You will feel the power of this feature when you start `fuzzy-finder` in
your home directory.


Available Commands
------------------


### `fuzzy-finder`

Open a new window and start a fuzzy finder process inside of it.
This package defines several variables which configure this command:
for example `fuzzy-finder-default-arguments` defines the arguments passed
to the fuzzy finder process.

By default, it recursively lists the current directory, starts a `fzf` process, and visits selected files.

This command can also be used as a function to define a new fuzzy finder command.
You can pass keyword arguments to overwrite the defaults.


### `fuzzy-finder-find-files-projectile`

Execute fuzzy finder and visit resulting files.

If the projectile package is available, start from the project root directory.

### `fuzzy-finder-goto-gitgrep-line`

Select lines with fuzzy finder and go to selected point in a git repository.

Run git grep command to generate input lines.


Limitation
----------

Currently this package does not work on Windows `cmd.exe` environment,
because current `term.el` library does not support running commands with
`cmd.exe`.
We sincerely welcome your
[contributions](https://github.com/10sr/fuzzy-finder-el/pulls) for this!



License
-------

This software is licensed under GPL version 3 or any later version.
See `LICENSE` for details.


[fzf]: https://github.com/junegunn/fzf
[peco]: https://github.com/peco/peco
[selecta]: https://github.com/garybernhardt/selecta
