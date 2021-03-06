VIM Configurations
==================

Building VIM from source
------------------------

```
sudo apt install ncurses-dev
wget https://github.com/vim/vim/archive/master.zip
unzip master.zip
cd vim-master
# If on a Ubuntu 16.04, replace lua5.1-dev as liblua5.1-dev.
sudo apt-get install libncurses5-dev libgnome2-dev libgnomeui-dev \
    libgtk2.0-dev libatk1.0-dev libbonoboui2-dev \
    libcairo2-dev libx11-dev libxpm-dev libxt-dev python-dev \
    python3-dev ruby-dev lua5.1 lua5.1-dev libperl-dev git
./configure --with-features=huge --enable-pythoninterp --enable-rubyinterp --enable-luainterp --enable-perlinterp --with-python-config-dir=/usr/lib/python2.7/config/ --enable-gui=gtk2 --enable-cscope --prefix=/usr
sudo make
sudo make install
```

VIM Plugins
-----------

- Install: vundle
  ```
  mkdir .vim
  cd .vim
  mkdir bundle 
  git clone https://github.com/VundleVim/Vundle.vim.git ~/.vim/bundle/Vundle.vim
  ```

- Install Ctags
  ```
  sudo apt-get install ctags
  ```

- Install YouCompleteMe

  ```
  sudo add-apt-repository ppa:jonathonf/vim
  sudo apt-get update
  sudo apt-get vim-gtk
  ```
  ```
  sudo apt-get install build-essential cmake
  sudo apt-get install python-dev python3-dev
  git clone https://github.com/Valloric/YouCompleteMe.git
  git submodule update --init --recursive
  cd ~/.vim/bundle/YouCompleteMe
  ./install.py --clang-completer
  ```

- Install Plugins
  ```
  vim
  :PluginInstall
  ```

- Configure Latex-suite
  + First of all, install the texlive.
  ```
  sudo apt-get install texlive-full
  ```

  + Edit .vim/bundle/LaTeX-Suite-aka-Vim-LaTeX/ftplugin/latex-suite/texrc

  + Set the targit format as pdf. Change line 83 into: 
  ```
  if has('macunix')
  TexLet g:Tex_DefaultTargetFormat = 'pdf'
  else
  TexLet g:Tex_DefaultTargetFormat = 'pdf' /*都生成pdf*/
  endif
  ``` 

  + Set builder as XeLateX. Change line 108 into:
  ```
  TexLet g:Tex_CompileRule_pdf = 'xelatex -interaction=nonstopmode $*' /*用xelatex进行编译*/
  ```

  + Set evince as the viewer. Change line 143 into:
  ```
  TexLet g:Tex_ViewRule_pdf = 'evince' /*用evince来预览生成的pdf*/
  ```
