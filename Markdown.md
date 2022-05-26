# Markdown Basics

## Stying
---

### Emphasis
Italic
Bold
```
*Emphasize* _emphasize_
**Strong** __Strong__
```

### Subscrip
Wrap around with single ~
```
H~2~0
```

### Superscript
Wrap with ^
```
x^2^
```

### Tables
```
| Syntax    | Description  |
| --------  | ------------ |
| Header    | Title        |
| Paragraph | Text         |
```

### Footnotes
```
I have more [^1] to say up here.

[^1]: To say down here.
```

### Definition List
```
term
: definition
```

### Strikethrough
```
~~~The world is flat.~~~
```



## Links & Images
---

### Inline Links
```
A [link](http://example.com "Title").

Results:

"A link."
```


### Referenced Link
Reference section can be anywhere in the document

```
Some text with [a link][1] and
another [link][2].

[1]: http://example.com/ "Title"
[2]: http://example.org/ "Title"

Results:

"Some text with a link and another link."
```


### Inline Images
The "Alt" text makes images accessible to visually impaired
```
go: ![Alt](/wp.png "Title")
```



## Lists
---

### Bullet Lists
```
    * Item
    * * Item
    * - Item
    * - Item
```

### Numbered Lists
```
1. Item
2. Item
```

### Task List
```
- [X] Write the task list
- [ ] Update
- [ ] Win
```
