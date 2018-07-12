# Quickstart

```bash
git clone git@github.com:smvoss/dotfiles.git ~/.dotfiles
pushd ~/.dotfiles
chmod +x bootstrap
# Install the dotfiles by symlinking into correct location
./bootstrap --symlink
popd
```

# Installation options

Certain options may be provided as comments at the top of dotfiles. These options and their uses are as follows:

| Option Name   | Description     | Usage  |
| ------------- | --------------- | ------ |
| `install-dir` | Location to install dotfile. Will default to $HOME | `install-dir /path/to/file` |
| `hidden`      | Whether the file should be created as a hidden file | `hidden <true \| false>` |

## Example: fzf plugin

fzf plugins go in a subfolder, `~/.fzf`, and should be installed as such. This can be achieved by specifying the `install-dir` option in the file:

```
# Dotfile bootstrap arguments
#   install-dir $HOME/.fzf/shell
```

# Ignored files and folders

Not everything should be installed, so a blacklist is created. The default blacklist can be found in the bootstrap, defined as an array named `IGNORE`.

This default blacklist will not cover everything you may not want to install when using `dotfile-bootstrap` as a submodule, so a file `bs_ignore.json` may be provided. This file must exist in the directory bootstrap is called from (which is currently restricted to the root of the repository).

This file must be an array of files and folders to be exempt. An example (shown below) will ignore a folder named `configs`, which could be used for bootstrap configs so they do not get installed.

```
[
  "configs/*"
]
```
