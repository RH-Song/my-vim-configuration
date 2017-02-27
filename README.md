VIM Configurations
==================

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
  + Edit .vim/bundle/LaTeX-Suite-aka-Vim-LaTeX/ftplugin/tex.vim

  + Set the targit format as pdf. Change line 89 into: 
  ```
  if has('macunix')
  TexLet g:Tex_DefaultTargetFormat = 'pdf'
  else
  TexLet g:Tex_DefaultTargetFormat = 'pdf' /*都生成pdf*/
  endif
  ``` 

  + Set builder as XeLateX. Change line 115 into:
  ```
  TexLet g:Tex_CompileRule_pdf = 'xelatex -interaction=nonstopmode $*' /*用xelatex进行编译*/
  ```

  + Set evince as the viewer. Change line 146 into:
  ```
  TexLet g:Tex_ViewRule_pdf = 'evince' /*用evince来预览生成的pdf*/
  ```
