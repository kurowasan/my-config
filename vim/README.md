# 1. Installing vim
It might be necessary to reinstall vim if it doesn't support python. To test it, you can execute `vim --version`. If python is supported you should see `+python` or `+python3`.
```
cd /tmp && git clone https://github.com/vim/vim.git && cd vim
./configure --enable-pythoninterp --prefix=/usr
make && sudo make install
```

# 2. Configuring vim
Copy the `.vimrc` file.

### Install the Powerline
Powerline is a useful statusline plugin for vim and your shell.
```
pip install --user powerline-status
git clone https://github.com/powerline/fonts
brew install powerline
```

### Install Vundle
Vundle is a package manager for vim:
```
git clone https://github.com/VundleVim/Vundle.vim.git ~/.vim/bundle/Vundle.vim
vim +PluginInstall +qall
```
### Install YouCompleteMe
YouCompleteMe is a code-completion engine that is really useful when coding:
```
brew install cmake python go nodejs
brew install mono
cd ~/.vim/bundle/YouCompleteMe
./install.py
```
For more detail on the installation see [this](https://github.com/ycm-core/YouCompleteMe#installation)

### Install Copilot
If you have a copilot account, follow these [instructions](https://ovid.github.io/articles/using-github-copilot-with-vim.html)

# 3. A quick overview of vim plugins
- __Nerdtree__ is a file system explorer. You launch it with `F2`. It is a vim buffer as any other: you can move, search, etc. `s` and `i` open a file in vertical and horizontal mode, respectively. As an alternative, you can use `fzf` to open files. Press `space-q` and type words in the file you are looking for.
- __surround__ you can easily "surround" selections with brackets, parens, quotes, etc. For example, after selecting a word in visual mode, `S)` would put parens around the word.
- __auto-pairs__ insert brackets, parens, quotes in pairs.
- __context.vim__ shows the context of your code. For example, you can see the function you are in as a header.
- __easymotion__ use `space-space-w` and then press the letter where you want to move!
- __ultisnips__ allows you to use snippets in Vim and __vim-snippets__ provides useful default snippets. To look at the existing snippets, you can type `:Snippets`. To add custom snippets, execute `:UltiSnipsEdit`. Copy the file `python.snippets` in `~/.vim/bundle/UltiSnips`. To autocomplete a snippet, type the word then `<ctrl-o>`.
- There are multiple other plugins specific to programming, for python, git, clojure, jekyll, etc.
