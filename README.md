**All these source files are from the Bluespec-provided installation package**

A basic BSV syntax highlighing mode for the vi clone VIM
(http://www.vim.org).  The mode is mostly written from scratch, with
two regexps copied from VIM's Verilog mode.

To use, create a ~/.vim directory for your vim settings, with
subdirectories ~/.vim/ftdetect , ~/.vim/indent and ~/.vim/syntax.
Then copy the files from ftdetect/ , indent/ and syntax/ to
~/.vim/ftdetect/ , ~/.vim/indent and ~/.vim/syntax/ respectively.

Or in unix terms tcsh: 

>   mkdir -p ~/.vim/ftdetect
>   mkdir -p ~/.vim/indent
>   mkdir -p ~/.vim/syntax
>  (cd $BLUESPECDIR/../util/vim; tar cf - *) | (cd ~/.vim; tar xvf -)
 
in your .tcshrc you may need to set the environment variable VIMRUNTIME

   setenv VIMRUNTIME /usr/share/vim/vim71

or in bash

   VIMRUNTIME=/usr/share/vim/vim71

verify this exists: older versions may have /usr/shar/vim/vim61

You may need to run " :syn on " once vim is running to enable syntax coloring

In order to enable BSV indenting, it is recommended to add the
following to your .vimrc file:

if has("autocmd")
 " Enabled file type detection
 " Enabled file language-dependent indenting
 filetype plugin on
 filetype indent on
endif " has ("autocmd")
let b:verilog_indent_modules = 1

