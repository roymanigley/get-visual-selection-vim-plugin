# get-visual-selection-vim-plugin
> The function `visual#get_current_selection()` returns the current visually selected text or an empty string 

## Installation
<details>
<summary>without plugin manager</summary>

1. In the terminal,
    ```bash
    mkdir -p ~/.vim/bundle/
    git clone https://github.com/roymanigley/get-visual-selection-vim-plugin.git ~/.vim/bundle/get-visual-selection-vim-plugin
    mkdir -p ~/.vim/plugin/
    ln -s ~/.vim/bundle/get-visual-selection-vim-plugin/plugin/visual.vim ~/.vim/plugin/visual.vim
    ```
1. Restart Vim
</details>


<details>
<summary>Pathogen</summary>
Pathogen is more of a runtime path manager than a plugin manager. You must clone the plugins' repositories yourself to a specific location, and Pathogen makes sure they are available in Vim.


1. In the terminal,
    ```bash
    git clone https://github.com/roymanigley/get-visual-selection-vim-plugin.git ~/.vim/bundle/.get-visual-selection-vim-plugin
    ```
1. In your `vimrc`,
    ```vim
    call pathogen#infect()
    syntax on
    filetype plugin indent on
    ```
1. Restart Vim
</details>

<details>
  <summary>Vundle</summary>

1. Install Vundle, according to its instructions.
1. Add the following text to your `vimrc`.
    ```vim
    call vundle#begin()
      Plugin 'roymanigley/get-visual-selection-vim-plugin'
    call vundle#end()
    ```
1. Restart Vim, and run the `:PluginInstall` statement to install your plugins.
</details>

<details>
  <summary>Vim-Plug</summary>

1. Install Vim-Plug, according to its instructions.
1. Add the following text to your `vimrc`.
```vim
call plug#begin()
  Plug 'roymanigley/get-visual-selection-vim-plugin'
call plug#end()
```
1. Restart Vim, and run the `:PlugInstall` statement to install your plugins.
</details>

<details>
  <summary>Dein</summary>

1. Install Dein, according to its instructions.
1. Add the following text to your `vimrc`.
    ```vim
    call dein#begin()
      call dein#add('roymanigley/get-visual-selection-vim-plugin')
    call dein#end()
    ```
1. Restart Vim, and run the `:call dein#install()` statement to install your plugins.
</details>

## Example Usage

> bind the keys `CTRL+L` to echo the current selected text  

    function TestSelection() 
        const selection = visual#get_current_selection() 
        echo selection
    endfunction

    "               <c-u> removes the range, otherwise it would be invoked for every line
    vnoremap <C-l> :<c-u>call TestSelection()<CR>
