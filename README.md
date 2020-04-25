# CMakeFormatVim

Vim plugin for the [cmake-format](https://github.com/cheshirekow/cmake_format) tool.

## How to use

### Install cmake-format

`cmake-format` is required - see https://github.com/cheshirekow/cmake_format for installation details.

The `cmake-format` executable needs to be available in the shell environment of the vim process.

### Install the plugin

Copy [cmake_format.vim](cmake_format.vim) into the vim plugin location:
```
cp cmake_format.vim ~/.vim/plugin/
```

### Bind a hotkey for executing the formatter

It is useful to bind a hotkey to invoke the formatting command.

For example, the following can be added to `.vimrc` to bind the key **F8** to trigger formatting:
```vimscript
" Run cmake-format to format the current buffer.
autocmd FileType cmake nnoremap <buffer><F8> :<C-u>CMakeFormat<CR>
autocmd FileType cmake vnoremap <buffer><F8> :CMakeFormat<CR>
```

## Planned work

- Add support for formatting the selected buffer subset, instead of the entire buffer.
