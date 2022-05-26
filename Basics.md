# Basics


### Enter Wiki

Show index of wiki page
```
<Leader> ww
```


### Create Link from inside index page

Write a page name anywhere + put cursor over, press enter


### Jump to Page

On an existing page link, press enter


### Go Back to Previous Page
```
<BS>
```


### Delete a Page
```
<Leader> wd
```


### Rename Page

With desired page open in editor

All links in other files will also be updated
```
<Leader> wr
```


### Diary
Go to / Create if doesn't exist Diary Directory:
```
<Leader> wi
```

Create new entry to today's date:
```
<Leader> w <Leader> w
```

Generate Newest to Oldest List:
```
<Leader> w <Leader> i
```


## Generate HTML of wiki
    Has to be vimwiki syntax

Just a single page
```
:Vimwiki2HTML
```



#### Wiki Cheatsheet
Link : https://gist.github.com/drkarl/4c503bccb62558dc85e8b1bc0f29e9cb

## Wiki Management
- [number] `<leader> ww` - open wiki index file
- [number] `<leader> wt` - open wiki index file in new tab
- `<leader> ws` - list and select available wikis
- `<leader> wd` - delete wiki page
- `<leader> wr` - rename wiki page


## Diary management
- [number] `<leader> wi` - open diary index file for wiki
- `<leader> w <leader> i` - update current diary index
- [number] `<leader> w <leader> w` - open today’s diary file for wiki
- [number] `<leader> w <leader> t` - open today’s diary file for wiki in new tab
- `<C-Up>` - open previous day’s diary
- `<C-Down>` - open next day’s diary


## Navigation
- `<CR>` - follow/create wiki link
- `<C-S-CR>` - follow/create wiki link in new tab
- `<backspace>` - go back to previous wiki page
- `<Tab>` - go to next link on current page
- `<S-Tab>` - go to previous link on current page


## Editing shortcuts
- `<C-Space>` - toggle list item on/off
- `=` - add header level
- `-` - remove header level
- `+` - create/decorate links
- `glm` - increase indent of list item
- `gll` - decrease indent of list item
- `gl*` or `gl8` - switch or insert “*” symbol
- `gl#` or `gl3` - switch or insert “#” symbol
- `gl-`  - switch or insert “-“ symbol
- `gl1`  - switch or insert “1.” symbol


## Table shortcuts
- `<A-Left>` move column left
- `<A-right>` move column right
- `<CR>`  (insert mode) go down/create cell
- `<Tab>` (insert mode) go next/create cell
- `gqq` or `gww`  reformat table


## Text objects
`ah`    section between 2 headings including empty trailing lines
`ih`    section between 2 headings excluding empty trailing lines
`a\`    table cell
`i\`    inner table cell
`ac`    table column
`ic`    inner table column
