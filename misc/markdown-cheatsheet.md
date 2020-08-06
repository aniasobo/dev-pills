# MD formatting - view me raw!

line break with 2 returns

**Two ways to bold**
**This is the other way**

_The two ways to italic_
_Also like this_

**_There are THREE ways to both_**
**_second way_**
_**THIRD WAY**_

| table         | column        | anothercol    |
| ------------- | ------------- | ------------- |
| text in col 1 | text in col 2 | text in col 3 |

KEYBOARD
<kbd>↵</kbd>
`⌘`

links!

[link to url](url)
![link to image](my.img)
[link to anchor](#anchor)
[link to local file](local-folder/file.txt)
autolink: <http://testwebsite.com/> (equivalent to `[http://testwebsite.com/](http://testwebsite.com/)`)
autolink email addresses like so: <foo@bar.com>

```
code snippet
```

`inline code snippet`

```diff
code with edits highlighted
- bad code
+ good code
```

Another way to make a code block in Markdown is to indent every line of the
block by at least 4 spaces or 1 tab.

This is a normal paragraph:

    This is a code block.

Here is an example of AppleScript:

    tell application "Foo"
        beep
    end tell

A code block continues until it reaches a line that is not indented
(or the end of the article).

> this is a blockquote
>
> > OMG a nested blockquote!
> > and back to what I was just quoting

Blockquotes can contain other Markdown elements, including headers, lists,
and code blocks:

> ## Header in a quote can you believe that shit
>
> 1.  Firstly
> 2.  Lastly
>
> Here's some code wow:
>
>     return shell_exec("echo $input | $markdown_script");

~strikethrough~
~~another way to strikethrough with two tildes~~

- nice list
- with dots

* another way to list
* with plus signs

- also hyphens
- can make lists
- [ ] any list can have a checkbox
- [x] tick it once done

### How to make a nested list

- start with your top-level list item
  - indent the nested item
  - and the next one
- now you have a nested list, but
  1.  you can also have a numbered nested list
      - that list can have its own child list
      - with n items
  2.  this one can have a todo list like so:
      - [x] make a list
      - [x] add some levels to it
      - [ ] don't make it meta

## Index / table of contents

Is populated automatically - just start adding anchor links to your headers as a list; add `<!-- omit in toc -->` to headline to omit it from the index

---

horizontal rules:

---

or:

---

also:

---

```
│   README.md
│   .env
│   .gitignore
│   demo.png
│   package.json
│   yarn.lock
└───public
│   │   index.html
└───src
│   │  App.js
│   │  index.js
│   └───tests
│   │      App.spec.js
│   └───components
│   │      Component.js
│   └───anotherNestedFolder
│   │      nestedFile.js
```

┌────────────────────┐
│ Box drawing chars │
└────────────────────┘

[MORE HERE](https://learnxinyminutes.com/docs/markdown/)

[AND MORE](https://raw.githubusercontent.com/mxstbr/markdown-test-file/master/TEST.md)

[EVEN MORE](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)
