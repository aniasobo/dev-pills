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

Save changes with `:w` FILENAME.

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

`R` to replace more than one char - <kbd>ESCAPE</kbd> marks the end of action.

Replace is similar to the Insert mode but every typed char REPLACES an existing char.

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

### ignore case

`:set ic`, then search

Ignore just once with `/phrase\c`

Disable ignore case with `:set noic`

### highlight searched phrase

`:set hls is` will highlight all instances of the searched phrase.

Remove highlight with `:nohlsearch`.

### partial matches

`:set is` shows partial matches for search phrase.

### remove setting

prepend `no` to any setting you want to cancel: `:set noic` will end `ignorecase`

## Matching parentheses - `%`

Cursor on the parentheses/bracket. Use `%` to jump from opening to closing bracket.

## SUBSTITUTE - `:s`

`:s/a/the` - substitute the first a on the line for the

`:s/a/the/g` - substitute - a for - the - globally on the line - final `c` adds prompt

`:1,3s/a/the/g` - substitute - a for - the - globally betweeen lines 1 and 3

`:%s/a/the/g` - substitute all a for the in entire file

`:%s/a/the/gc` - as above, with confirmation prompt for each occurence.

## External command: `:!`

`:!` followed by an external command.

`:` sets the cursor at the bottom of the screen where it awaits instruction. `!` lets you execute **any external shell command**.

`:!ls` <kbd>ENTER</kbd> lets you see your directory's listing.

## Writing to files

Save with `:w` followed by filename.

If you can't find filename, use the `:!ls` command.

Use `:w` new filename to save the current file under a new name.

Delete file with `!rm` FILENAME.

## More file operations

`v` is for Visual selection.

Select text with `v` - once the `v` is hit, you're in selection mode and can move cursor to the end of the selection.

Then press `:` - a prompt appears at the bottom. Save selection with `w filename`.

Insert contents of a file with `:r` FILENAME below cursor.

You can also insert the output of console with `:r !ls` etc

## OPEN - `o` / `O`

`o` places you in insert mode and opens a new line below the cursor.

`O` places you in insert mode with new line above the cursor.

## APPEND - `a`

`a` places you in insert mode, appends after the cursor. Similar to `i`.

## COPY `y` - PASTE `p`

With `v` visual mode, select text, then `y` yank/copy it; move the cursor, paste it with `p`, then exit with <kbd>ESC</kbd>

`yw` copies one word.

## HELP

In vim, type `:help`

Close help with `:q`

There are many help options, like:

- `:help insert-index` for insert mode options
- `:help user-manual` for full TOC
- `:help vimrc-intro` for `vimrc` help
- `:help w` for motion options, etc

## Command line completion

Make sure vim is not in compatible mode with `:set nocp`

start with `:e`, then <kbd>CTRL</kbd> `D` for a list of available commands starting with e. `d` <kbd>TAB</kbd> to select one.

Especially useful for help.

## Creating a `vimrc` startup script

[here's one](https://github.com/colepeters/dotfiles/blob/master/vimrc)

[here's another](https://github.com/skwp/dotfiles/blob/master/vimrc)

Start editing your `vimrc` with `:e ~/.vimrc`

Read example `vimrc` with `:r $VIMRUNTIME/vimrc_example.vim`

Write the file with `:w`

`:help vimrc-intro`

[my current vimrc](https://github.com/aniasobo/dotfiles/blob/master/vimrc)
