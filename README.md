[toc]
# item2
https://iterm2.com/downloads.html

# brew
``` zsh 
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"

# enable cask-fonts/cask
brew tap homebrew/cask-fonts
``` 

# syncthing
``` zsh 
brew install --cask syncthing

# Only if this is the first device
# mkdir ~/Sync/conf/

ln -s -f ~/Sync/conf/.zshrc ~/
```

# oh-my-zsh
``` zsh
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

# tmux
```
brew install tmux

brew install reattach-to-user-namespace

git clone https://github.com/tmux-plugins/tpm ~/.tmux/plugins/tpm

ln -s -f ~/Sync/conf/.tmux.conf ~/
```
config iterm2 run "tmux" when startup

iterm2 -> profile -> Send text to at start: 
```
tmux ls && read session && tmux attach -t ${session:-default} || tmux  new -s ${session:-default}"
```
# pyenv
``` zsh
brew install pyenv
brew install pyenv-virtualenv
# echo 'eval "$(pyenv init -)"' >> ~/.zshrc
# echo 'eval "$(pyenv virtualenv-init -)"' >> ~/.zshrc

# if install error like: error: implicit declaration of function 'sendfile' is invalid in C99
# ref: https://github.com/pyenv/pyenv/issues/1643

pyenv install 3.8.1
pyenv global 3.8.1
pip install -U pip
pip install ipython flake8 flake8-bugbear mccabe pycodestyle pyflakes python-lsp-server typing-extensions black


```

# neovim
``` zsh
brew install neovim

ln -s -f ~/Sync/conf/nvim/init.vim ~/.config/nvim/init.vim
```
* plugins
```
sh -c 'curl -fLo "${XDG_DATA_HOME:-$HOME/.local/share}"/nvim/site/autoload/plug.vim --create-dirs https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim'
```
open nvim and
```
:PlugInstall
```
