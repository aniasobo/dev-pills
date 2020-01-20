# MD formatting - view me raw!

line break with 2 returns  

**Two ways to bold**
__This is the other way__
   
_The two ways to italic_
*Also like this*

***There are THREE ways to both***
**_second way_**
*__THIRD WAY__*



table | column | anothercol
------ | ------ | ---------
text in col 1 | text in col 2 | text in col 3

KEYBOARD
<kbd>Ctrl</kbd>
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

> this is a blockquote
> > OMG a nested blockquote!  
> and back to what I was just quoting

~strikethrough~
~~another way to strikethrough~~

* nice list
* with dots

+ another way to list
+ with plus signs

- also hyphens
- can make lists
- [ ] any list can have a checkbox
- [x] tick it once done 

### How to make a nested list

* start with your top-level list item
   * indent the nested item
   * and the next one
* now you have a nested list, but
   1. you can also have a numbered nested list 
      - that list can have its own child list
      - with n items
   2. this one can have a todo list like so:
      - [x] make a list
      - [x] add some levels to it
      - [ ] don't make it meta

## Index / table of contents

Is populated automatically - just start adding anchor links to your headers as a list; add `<!-- omit in toc -->` to headline to omit it from the index

---

horizontal rules:

***

or:

- - - 

also:

*********
     
```
project structure
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

[MORE HERE](https://learnxinyminutes.com/docs/markdown/)

[EVEN MORE](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)

