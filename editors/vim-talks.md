# Notes from various Vim talks

## Going mouseless with Vim, Tmux and Hotkeys

[LINK](https://www.youtube.com/watch?v=E-ZbrtoSuzw&feature=youtu.be)

**Modes**

| Mode              | Trigger keys                    |
| ----------------- | ------------------------------- |
| Normal mode       | <kbd>ESC</kbd>                  |
| Insert mode       | `i`, `a`, `c`                   |
| Visual mode       | `v`, `V`, <kbd>CTRL</kbd> + `v` |
| Command-line mode | `:`, `/`                        |

**Example: [count][operator][text object / motion] samples**

`6+` = 6x go down to line start
`gUaW` = capitalize a WORD
`3ce` = 3x change to word end
`4$` = 4x go to end of line
`d]m` = delete to start of next method
`%` = jump to match of next paren or bracket

**Scrolling motions**

```
    ^
    H
    zt

<   M   >
    zz

    L
    zb
    v
```

<kbd>CTRL</kbd> + `U` for up

<kbd>CTRL</kbd> + `D` for down

<kbd>CTRL</kbd> + `B` for back

<kbd>CTRL</kbd> + `f` for forward

**Search**

`*` search forward for word under cursor

`#` search back for word under cursor

`gd` go to local declaration

`/` <kbd>ENTER</kbd> - search for last used pattern

`?` <kbd>ENTER</kbd> - search back for last used pattern

`[count]n` repeat last search `[count]` times

`[count]N` repeat last search back `[count]` times

**Tags**

<kbd>CTRL</kbd> + `]` jump to keyword definition

<kbd>CTRL</kbd> + `t` pop from the tag stack

**Navigation**

`:e[dit] {file}`

`:f[ind] {file}`

`gf` go to file

**Jumps**

<kbd>CTRL</kbd> + `O` / <kbd>CTRL</kbd> + `I` - cycle through jumplist

`:g` / `g` to cycle through changes

**Using buffers**

> Tabs for window containers
> Windows for buffer viewports
> Buffers for file proxies (and the arglist)

Use the buffer-centric workflow instead of traditional tabs.

| Trigger            | Buffer action                       |
| ------------------ | ----------------------------------- |
| `:bn`              | go to next buffer                   |
| `:b {filename}`    | go to buffer `{filename}`           |
| `:bd`              | delete current buffer               |
| `:buffers`         | print out all buffers               |
| `:bufdo {cmd}`     | execute `{cmd}` for all buffers     |
| `:n`               | go to next file based on arglist    |
| `:arga {filename}` | add `{filename}` to arg list        |
| `:argl {files}`    | make a local arg copy via `{files}` |
| `:args`            | print out all args                  |

**Buffers** - every single file you've opened in vim

**Arguments** - exactly the files you opened when you started vim

add windows commands here

TABS ARE FOR WINDOW COLLECTIONS
