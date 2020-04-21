# dotfiles

Clone into `~/.dotfiles`.

## Prerequisites

* The bash config expects [liquidprompt](https://github.com/nojhan/liquidprompt) to be
  installed.
* The tmux config expects `xclip` to be installed.
* Install the [vim-tmux-navigator](https://github.com/christoomey/vim-tmux-navigator)
  plugin for vim and neovim.

## Bash

Append the following lines to `~/.bashrc`:

```sh
# Load custom configuration.
if [ -f ~/.dotfiles/bashrc_custom ]; then
    . "$HOME/.dotfiles/bashrc_custom"
fi
```

In addition to some `bash` settings, custom settings are included for
the following:
* [Go](https://golang.org/)
* [Elixir](https://elixir-lang.org/)
* [Node](https://nodejs.org/)
* [Python](https://www.python.org/)
  * [pyenv](https://github.com/pyenv/pyenv)

## Tmux

Create symlink for the config file and install the plugin manager.

```sh
ln -s ~/.dotfiles/tmux.conf ~/.tmux.conf
git clone https://github.com/tmux-plugins/tpm ~/.tmux/plugins/tpm
```

## Tig

Add the following to `~/.tigrc`:

```
source ~/.dotfiles/tigrc
```

## Python

Install [pyenv][pyenv] and [pyenv-virtualenv][pyenv-virtualenv].

[pyenv]: https://github.com/pyenv/pyenv
[pyenv-virtualenv]: https://github.com/pyenv/pyenv-virtualenv

Example usage:

```bash
~$ pyenv install 3.8.2
~$ mkdir ~/myproject
~$ cd ~/myproject
~/myproject$ pyenv virtualenv 3.8.2 myproject
~/myproject$ pyenv local myproject
```

The virtualenv will be automatically activated whenever you enter the projet's
directory.
