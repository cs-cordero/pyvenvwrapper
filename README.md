## Pyvenvwrapper

A set of helper functions written in Bash that allow you to manage your Python3
venv environment in a convenient way.
These functions are small improvements over similar bash scripts floating
around the internet that implement these functions.

## Requirements
* `Python3` and `Python3-venv` (obviously).
* A UNIX shell with some standard programs/commands, i.e., `command`,
  `basename`, `mkdir`, `ls`.

## Installation
Since the script simply exposes some global functions into your bash session
you can pretty much do whatever you want to install it -- you just need to make
sure that the file gets `source`d somehow.  Here are two options:
* Option 1:  Copy the `.pyvenvwrapper` file anywhere onto your machine, then
  add `source /path/to/.pyvenvwrapper` to your `.bashrc` or `.bash_profile`.
* Option 2:  Copy the source code in `.pyvenvwrapper` into your `~/.bashrc` or
  `~/.bash_profile` file.

## Helper Functions

All virtual environments are stored in a `~/.venv` folder by default.

You can change this folder to whichever folder you prefer by exporting a
`VENV_HOME` variable _before_ sourcing `.pyvenvwrapper`.

#### `mkvenv [env-name]`
Creates a python virtual environment at `$VENV_HOME/[env-name]`.

#### `rmvenv [env-name]`
Deletes a python virtual environment at `$VENV_HOME/[env-name]`.

#### `lsvenv`
Provides a list of environment names currently stored in `$VENV_HOME`

#### `activate [env-name]`
Activates the environment located at `$VENV_HOME/[env-name]`.  No need to
source the `activate` script in the environment folder!

#### `workon [env-name]`
Activates the environment loated at `$VENV_HOME/[env-name]` and changes your
directory to `$VENV_PROJECT_FOLDER/[env-name]`.

#### `mkproj [env-name]`
Creates a python virtual environment at `$VENV_HOME/[env-name]`, then creates a
directory at `$VENV_PROJECT_FOLDER/[env-name]`, and then finally changes your
directory to that new directory.

#### `deactivate`
Deactivates the currently active environment (if any).

## Environment Variables

#### `VENV_HOME` (default: $HOME/.venv)
Root folder where all python virtual environments are created.

#### `VENV_PROJECT_DIRECTORY` (default: $HOME/Projects)
Root folder where all python projects are created.  This is where your source
files go.

#### `VENV_NO_PROJ` (default: unset)
Set this to any value if you don't want to use a VENV_PROJECT_DIRECTORY and you
don't care whether it exists or not.  This may affect whether `workon` and/or
`mkproj` commands are available to you.

#### `VENV_SKIP_PIP_UPGRADE` (default: unset)
Set this to any value if you don't want the `mkvenv` to upgrade pip to the
latest version immediately after creating the environment.

## Author

* **Christopher Sabater Cordero** - [cs-cordero](https://github.com/cs-cordero)
