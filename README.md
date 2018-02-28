## Pyvenvwrapper

A set of helper functions written in Bash that allow you to manage your Python3 venv environment in a convenient way.
These functions are small improvements over similar bash scripts floating around the internet that implement these functions.

## Requirements
* `Python3` and `Python3-venv` (obviously).
* A UNIX shell with some standard programs/commands, i.e., `command`, `basename`, `mkdir`, `ls`.

## Installation
Since the script simply exposes some global functions into your bash session you can pretty much do whatever you want to install it -- you just need to make sure that the file gets `source`d somehow.  Here are two options:
* Option 1:  Copy the `.pyvenvwrapper` file anywhere onto your machine, then add `source /path/to/.pyvenvwrapper` to your `.bashrc` or `.bash_profile`.
* Option 2:  Copy the source code in `.pyvenvwrapper` into your `~/.bashrc` or `~/.bash_profile` file.

## Helper Functions

All virtual environments are stored in a `~/.venv` folder.

#### `mkvenv [env-name]`
Creates a python virtual environment at `~/.venv/[env-name]`.

#### `rmvenv [env-name]`
Deletes a python virtual environment at `~/.venv/[env-name]`.

#### `lsvenv`
Provides a list of environment names currently stored in `~/.venv`

#### `activate [env-name]`
Activates the environment located at `~/.venv/[env-name]`.  No need to source the `activate` script in the environment folder!

#### `deactivate`
Deactivates the currently active environment (if any).

## Author

* **Christopher Sabater Cordero** - [cs-cordero](https://github.com/cs-cordero)
