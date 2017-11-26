# dotfiles

Clone into `~/.dotfiles`.

## Prerequisites

* The bash config expects [liquidprompt](https://github.com/nojhan/liquidprompt) to be
  installed.
* The tmux config expects `xclip` to be installed.
* Install the [vim-tmux-navigator](https://github.com/christoomey/vim-tmux-navigator)
  plugin for vim and neovim.

## Bash

Add the following lines to `~/.bashrc`:

```sh
# Load custom configuration.
if [ -f ~/.dotfiles/bashrc_custom ]; then
    . ~/.dotfiles/bashrc_custom
fi
```

In addition to some `bash` settings, custom settings are included for
the following:
* [Go](https://golang.org/)
* [Elixir](https://elixir-lang.org/)
* [Node](https://nodejs.org/)
* [Python](https://www.python.org/)
  * [virtualenvwrapper](https://virtualenvwrapper.readthedocs.io/en/latest/)
  * [pyenv](https://github.com/pyenv/pyenv)

## Other

Create symlinks for the various config files.

```sh
ln -s ~/.dotfiles/tmux.conf ~/.tmux.conf
```
