# VSC + Vim

## Insert mode

Enter insert mode with `i` for typing.

If it doesn't work, `esc` will exit current mode.

## Back to normal mode

`Esc` or `Ctrl` + `c`

---

## Move around

### Cursor motions

Navigate cursor with `hjkl`

**MNEMONIC TIME!!**

`h` is for HIND

`j` is for JORD

`k` is for KOSMOS

`l` is for LAW IS RIGHT

### Word motions

Horizontally WORD by WORD with `w` forward and `b` backward.

Jump to end of word with `e` forward and `ge` backward.

Capitalise the above (`W`, `B`, `E`, `gE`) to consider special characters words.

### Character motions

Find the next occurence of char in current line with `f{char}`, backwards with `F{char}`. The next occurence over with `;`, previous occurence with `,`

Move the cursor to just before the next occurence of char with `t{char}`.

### Horizontal extremes

First char in line `0`

First non-blank char of line `^`

End of line `$`

Last non-blank char of line `g_`

### Vertical movement

Jump entire paragraph down `}`

Jump paragraph up `{`

Move down half a page `Ctrl D`

Move up half a page `Ctrl U`

### Vertical pattern search

Search forward with `/{pattern}`

Search backward with `?{pattern}`

`Enter` and `n`/`N` to start navigating through search results.

Run your last search with `/Enter` forwards and `?Enter` backwards.

Search for the word under the cursor with `*`.

### Add counts to movement commands

`{count}motion` so `2w` moves the cursor 2 words forward.

Good to combine with `j` and `k`

### Move semantically

Jump to definition of word under cursor `gd`

Jump to file in an import `gf`

### Core motions

Top of file `gg`

Specific line `{line}gg`

End of file `G`

Jump to closing bracket with `%`

---

# Operators

coming up


[Source](https://www.barbarianmeetscoding.com/blog/2019/02/08/boost-your-coding-fu-with-vscode-and-vim)
