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

## DELETE - `x` and `d`

- `x` deletes current char
- `dw` to delete a word in normal mode - cursor on start of word
- `d$` to delete from cursor position to the end of the line
- `dd` delete entire current line

### operator + motion

`d` + `motion`:

`d` is the delete operator. Some motions:

- `w` until the start of next word, EXCLUDING first char
- `e` to the end of current word, INCLUDING last char
- `$` to the end of the line, INCLUDING last char

### count + motion

- `2w` move the cursor 2 words forward
- `3e` move the cursor to the end of 3rd word forward
- `2dd` delete given number of lines
- `0` to move to start of the line
- `$` end of line

### operator + count + motion

- `d2w` deletes 2 words from the cursor position on

## UNDO - `u`

`u` to undo

`U` to fix the entire line

redo with <kbd>CTRL</kbd> + `r`

## PUT - `p`

`p` to put previously deleted text after the cursor.

To move lines around: `dd`, then move cursor to one line above where you want to put it; `p` to put it below cursor.

## REPLACE - `r`

With cursor over a character: `x` deletes character, `rx` replaces it with `x`

## CHANGE - `c`

Change until the end of word: `ce` followed by your chars, then <kbd>ESC</kbd> to move on from that word.

`ce` places you in insert mode!

Use with the same motions as delete! `c$` will enter insert mode and delete to the end of line.

`c` + number + motion like with delete too.

## File status and cursor

<kbd>CTRL</kbd> + `g` shows your location in the file and the file status.

`G` to move to the bottom of the file.

`gg` to move to the top of the file.

`507` and then `G` to move to that line.

## SEARCH - `/` and `?`

`/` followed by search phrase to search forward.

`?` followed by search phrase to search backward.

`n` and `N` to skip through search results ff and back.

<kbd>CTRL</kbd> + `o` to go back to where you began search.

<kbd>CTRL</kbd> + `i` to go forward.

## Matching parentheses - `%`

Cursor on the parentheses/bracket. Use `%` to jump from opening to closing bracket.

## SUBSTITUTE - `:s`
