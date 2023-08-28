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

### Install Copilot
If you have a copilot account, follow these [instructions](https://ovid.github.io/articles/using-github-copilot-with-vim.html)

# 3. A quick overview of vim plugins
- _Nerdtree_ is a file system explorer. You launch it with `F2`. It is a vim buffer as any other: you can move, search, etc. `s` and `i` open a file in vertical and horizontal mode, respectively.
- _surround_ you can easily "surround" selections with brackets, parens, quotes, etc. For example, after selecting a word in visual mode, `S)` would put parens around the word.
- _auto-pairs_ insert brackets, parens, quotes in pairs.
- _context.vim_ shows the context of your code. For example, you can the function you are in as a header.
- _easymotion_ use `space-space-w` and then press the letter where you want to move!
- _ultisnips_ allows you to use snippets in Vim and _vim-snippets_ provides useful default snippets. To look at the existing snippets, you can type `:Snippets`. To add custom snippets, execute `:UltiSnipsEdit`. Copy the file `python.snippets` in `~/.vim/UltiSnips`. To autocomplete a snippet, type the word then `<ctrl-o>`.
- There are multiple other plugins specific to programming, for python, git, clojure, jekyll, etc.
