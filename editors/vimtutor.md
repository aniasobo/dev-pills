# Notes from `vimtutor`

```
        ^
        k
< h           l >
        j
        v
```

<kbd>ESC</kbd> to exit vim modes.
Exit without save: `:q!` <kbd>ENTER</kbd>.
Exit with save: `:wq` (when editing a file), then exit.

Edit text: cursor over the character to delete, then `x`.

Insertion mode: press `i`. <kbd>ESC</kbd> to exit mode.

Append mode: `a`.

Open file with `$ vim filename` or in neovim `$ nvim filename`

Deletion:

- `dw` to delete a word in normal mode - cursor on start of word
- `d$` to delete from cursor position to the end of the line
