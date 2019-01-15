# dotfiles

Clone into `~/.dotfiles`.

## Prerequisites

* The bash config expects [liquidprompt](https://github.com/nojhan/liquidprompt) to be
  installed.
* The tmux config expects `xclip` to be installed.
* Install the [vim-tmux-navigator](https://github.com/christoomey/vim-tmux-navigator)
  plugin for vim and neovim.
* To install virtualenvwrapper: `pip3 install --user virtualenvwrapper`

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

## Tmux

Create symlink for the config file and install the plugin manager.

```sh
ln -s ~/.dotfiles/tmux.conf ~/.tmux.conf
git clone https://github.com/tmux-plugins/tpm ~/.tmux/plugins/tpm
```
