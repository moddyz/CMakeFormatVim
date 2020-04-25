# CMakeFormatVim

Vim plugin for auto-formatting CMake files.

## Installation

### Install cmake-format 

The **cmake-format** tool is required - see https://github.com/cheshirekow/cmake_format for installation details.

The `cmake-format` executable needs to be available in the shell environment of the vim process.

### Install the vim plugin

Clone this repository, and copy [cmake_format.vim](cmake_format.vim) into the vim plugin discovery location:
```bash
git clone git@github.com:moddyz/CMakeFormatVim.git
cd CMakeFormatVim
mkdir -p ~/.vim/plugin/
cp cmake_format.vim ~/.vim/plugin/
```

## Options

### Hotkey binding

It is useful to bind a hotkey to execute the formatter.

In your `~/.vimrc`, file type plugin detection needs to be on:
```vim
filetype plugin on
```

For example, the following can be added to `.vimrc` to bind the key **F8** to trigger formatting:
```vim
" Run cmake-format on the current buffer.
autocmd FileType cmake nnoremap <buffer><F8> :<C-u>CMakeFormat<CR>
autocmd FileType cmake vnoremap <buffer><F8> :CMakeFormat<CR>
```

### Additional arguments

Additional arguments can be set on the `g:cmake_format_args` global variable, to change cmake formatting behavior.  

These additional arguments are passed directly as command line arguments to the `cmake-format` executable.

For example, the following can be set in `.vimrc` to layout cmake directive subgroups and arguments vertically:
```
let g:cmake_format_args = "--max-subgroups-hwrap 0 --max-pargs-hwrap 0"
```

## Planned work

- Add support for formatting the selected buffer subset, instead of the entire buffer.
