# Making Terminal Sexy!

## Rough Notes [to check]

### Scheme1 [On Black Background]:   
#### Terminal
Add following to `~/.bashrc`, and then `"> source ~/.bashrc"`

```
  export PS1="\[\033[36m\]\u\[\033[m\]@\[\033[32m\]\h:\[\033[33;1m\]\w [\033[m\]\$ " 
  export CLICOLOR=1 
  export LSCOLORS=GxFxBxDxCxegedabagacad 
  alias ls='ls -GFh' 
```
 
Color and Effects: Black 
Text: White 
Cursor: Orange 
Check all : Use bold fonts, Allow blinking text, Display ANSI colors and use bright colors for bold text 
Selection: HSB Sliders (Hue: 359, Saturation: 44%, Brightness:24%) 

 
#### Vim
Add following to `~/.vimrc`,
```
  syntax on  
  set background=dark 
  hi Comment ctermfg=DarkGrey 
  hi String ctermfg=DarkBlue 
```
### Solarized Scheme for everything: 
Instructions: https://xuri.me/2013/11/09/use-solarized-color-scheme-in-os-x-terminal.html 

 

#### Terminal
1. git clone `git://github.com/altercation/solarized.git`
2. open `solarized/osx-terminal.app-colors-solarized/Solarized\ Dark\ ansi.terminal`
3. Set as default from preferences, and change font-size to 18, and Highlight brightness to 35%, Declare Terminal as: xterm-256 color 
4. Add following to `~/.bashrc`, and then `"> source ~/.bashrc"` 
```
export PS1="\[\033[36m\]\u\[\033[m\]@\[\033[32m\]\h:\[\033[33;1m\]\w\[\033[m\]\$ " 
export LC_ALL=en_US.UTF-8 
export LANG=en_US.UTF-8 
export CLICOLOR=1 
export LSCOLORS=GxFxBxDxCxegedabagacad 
export GREP_OPTIONS='--color=auto' 
```
5. `$ git clone https://github.com/huyz/dircolors-solarized `
6. `$ cp dircolors-solarized/dircolors.ansi-dark ~/.dircolors.ansi-dark `
7. `$ dircolors -p > ~/.dir_colors (optional – try without this) '
8. Add following to `~/.profile` and then `source` 
9. eval `dircolors ~/.dircolors.ansi-dark` 

#### Vim
```
$ cd solarized 
$ cd vim-colors-solarized/colors 
$ mkdir -p ~/.vim/colors 
$ cp solarized/vim-colors-solarized/colors/solarized.vim ~/.vim/colors/ 
$ vi ~/.vimrc 
    syntax on 
    if !has('gui_running') 
      let g:solarized_termtrans=1 
    endif 
    let g:solarized_termcolors=256 
    set background=dark 
    colorscheme solarized 
```


#### For SSH machines like LC computers 

Repeat the vim stuff as above , and

1. `$ git clone https://github.com/huyz/dircolors-solarized `
2. `cp dircolors-solarized/dircolors.ansi-dark ~/.dircolors.ansi-dark `
3. `dircolors -p > ~/.dir_colors` (optional – try without this) 
4 Add following to `~/.bashrc` or `~/.bash_profile`, and then source 
```
export PS1="\[\033[36m\]\u\[\033[m\]@\[\033[32m\]\h:\[\033[33;1m\]\w\[\033[m\]\$ " 
export LC_ALL=en_US.UTF-8 
export LANG=en_US.UTF-8 
export GREP_OPTIONS='--color=auto' 
alias ls='ls -G' 
alias ls='ls --color=auto' 
eval `dircolors ~/.dircolors.ansi-dark` 
```

#### ~/.bash_profile for iMAC [to look at if things doesn't work] 
```
# added by Mohit for CUDA/cuDNN/Tensorflow installation 
export CUDA_ROOT=~/program/cuda 
export PATH=~/program/cuda/bin${PATH:+:${PATH}} 
export CUDA_HOME=~/program/cuda 
export DYLD_LIBRARY_PATH="$CUDA_HOME/lib:$CUDA_HOME:$CUDA_HOME/extras/CUPTI/lib" 
export LD_LIBRARY_PATH=$DYLD_LIBRARY_PATH 
 
# Added by Mohit for Colours 
export PS1="\[\033[36m\]\u\[\033[m\]@\[\033[32m\]\h:\[\033[33;1m\]\w\[\033[m\]\$ " 
export LC_ALL=en_US.UTF-8 
export LANG=en_US.UTF-8 
export CLICOLOR=1 
export LSCOLORS=GxFxBxDxCxegedabagacad 
export GREP_OPTIONS='--color=auto' 
```
                                  
