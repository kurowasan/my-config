# Quick setup

Here is my setup for my shell. I use __Z shell__, an extended Bourne shell, with __oh-my-zsh__ for its configuration. I also use __fzf__ which is a fuzzy finder. Finally, I use __tmux__ which is a terminal multiplexer: ie, you can switch between terminals and detach/attach to them.

__Disclaimer:__ The commands and configurations are not my original work, I have mostly copied and put together configuration that I like and find useful.

__Summary:__
1. Install zsh, fzf, oh-my-zsh, tmux
2. Configuring
3. Basic how to use

# 1. Installing zsh, fzf, oh-my-zsh, tmux
### Installing zsh
To install zsh and set it as default, follow these [instructions](https://github.com/ohmyzsh/ohmyzsh/wiki/Installing-ZSH).

The two main steps are:
```
brew install zsh
```
```
chsh -s $(which zsh)
```

### Installing fzf
To install fzf, execute this and answer yes for all the questions:
```
git clone --depth 1 https://github.com/junegunn/fzf.git ~/.fzf
~/.fzf/install
```
For more detail on the fzf installation, see [this](https://github.com/junegunn/fzf#installation)


### Installing oh-my-zsh
To install oh-my-zsh, execute this:
```
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```
For more detail on the oh-my-zsh installation, see [this](https://ohmyz.sh/#install)

To install the oh-my-zsh plugins, run:
```
git clone https://github.com/zsh-users/zsh-autosuggestions ~/.oh-my-zsh/custom/plugins/zsh-autosuggestions

git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ~/.oh-my-zsh/custom/plugins/zsh-syntax-highlighting
```

### Installing tmux
```
brew install tmux
```


# 2. Configuring
To configure, just use the files (`.zshrc`, `.tmux.conf`, `agnoster.zsh-theme`) of this repo. For zsh and tmux, replace the `.zshrc` and `.tmux.conf` files on your home with the ones on the repo. For `agnoster.zsh-theme`, copy it in `~/.oh-my-zsh/themes`. For `.zshrc`, compared to the original file, it mainly changes the following lines:
```
ZSH_THEME="agnoster"
```
I prefer this theme, this is purely aesthetic.

```
plugins=(git vi-mode zsh-autosuggestions)
```
The plugin `vi-mode` allows you to use vim in the command line and `zsh-autosuggestions` will add an autocompletion feature. Lastly, the following add fzf:
```
[ -f ~/.fzf.zsh ] && source ~/.fzf.zsh

bindkey -s '^e' 'vim $(fzf)\n'
cs() { cd "$1" && ls; }
```


# 3. Basic how to use
- For zsh, you don't need to do anything special, you should now have a really useful autocompletion in your shell.
- For fzf, the most important functionalities are: `ctrl-t` and `ctrl-r` to respectively find files on your system or find commands in your history.
- For tmux, execute `tmux` to start it. Then, to create new panes, use `ctrl--` or `ctrl-|` for horizontal and vertical pane. To move between panes, use `ctrl` with the directional keys `hjkl` as in vim.
