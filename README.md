# dotfiles

Clone into `~/.dotfiles`.

## Prerequisites

- Install [mise](https://mise.jdx.dev/).
- The bash config expects [liquidprompt](https://github.com/nojhan/liquidprompt) to be
  installed.
- If using tmux:
  - The tmux config expects `xclip` to be installed.
  - Install the [vim-tmux-navigator](https://github.com/christoomey/vim-tmux-navigator)
    plugin for vim and neovim.

## Initial setup

Append the following lines to `~/.bashrc`:

```sh
# Load custom configuration.
if [ -f ~/.dotfiles/bashrc_custom ]; then
  . "$HOME/.dotfiles/bashrc_custom"
fi
```

Open a new terminal and run `mise doctor` to make sure `mise` is set up correctly.

Install dev tools:

```sh
mise use -g go@1.23
mise use -g node@22
mise use -g python@3.12
```

## Tmux (optional)

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

Example project `mise.toml`:

```toml
[tools]
python = "3.12"

[env]
_.python.venv = { path = ".venv", create = true }

ENV = "dev"
DATABASE_URL = "..."
```

### IPython

Create the default config, if it doesn't yet exist:

```bash
$ ipython profile create
```

Set the following in `~/.ipython/profile_default/ipython_config.py`:

```
c.TerminalInteractiveShell.true_color = True
```
