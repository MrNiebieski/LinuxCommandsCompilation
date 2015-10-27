##vim related##

---
###_shortcuts_###

    :sp filename

open `filename` in a split window.

Another way is `Ctrl+w+v`  then do:

    :e filename

Note that `<tab>` works under this option.

tab expolorer:

    :Te

`gt`, `gT` to move between tabs.

similarly ther are:

    :He
    :Ve
    :E
    :vsp

`ctrl+g` show filename and line.

---
###_moving around_###
---

`ctrl+u`, `ctrl+d` moves down and up by half a screen.

`ctrl+f`, `ctrl+b` moves down and up by one screen.

`z` then `enter`, move current line to the top of the screen.

`H` moves to the first line on the screen. `M` to the middle and `L` to the last line.

`G` to the last line of this file, `gg` to the first line of this file.

`O` begin a new line above the curosr and enter insert mode. `o` is below the cursor.

`%` shortcut for jumping between matching brackets.

`#` and `*` find previous and next identifier.

`(` and `)` move around by _sentences_.

`{` and `}` move around by _paragraph_.


`[[`, `]]` move to previous and next function.


`yy` or `Y` to copy, and `dd` to delete. 

`D` delete to the end of this line.


`192.168.1.1` is a single `WORD`.

`192.168.1.1` are 7 `word`s.

`W`,`B` moves around in terms of `WORDS`

`w`,`b` moves around in terms of `words`


---
###_change and modify_###
---

`u` undo change

`>>`,`<<` are used to indent and unindent line.

`==` auto indentation.


the difference beteween `0` and `^` is that `^` moves to the first non-white character. 

`$` moves to the last character.

`Ctrl+w+v` split window vertically.

`number` then `|`: goto colums.

`f<c>` moves _within_ a line to the next `c` character.

convert `<eol>`: `:set fileformat=unix` then `:w`


    vimdiff <file1> <file2>


toggle whitespace:

    :set list!


replace a single character:

    r<c>

delete a single character:

    x

`:cope` after `:make` to navigate around error and warnings.
`:cn`,`:cp` to move around.

to view changes:

    :changes

`g;` got to older change, `g,` goto newer change. Will not reset when exit.


###_registers_###

`+` or `*`: clipboard. `"` last del/copy, `%` filename.

example:

`"+p` paste system clipboard. (can be shared with bash shell.)

---
###_mark_###
---

quick start:

set mark:

    m<a-zA-Z>

goto mark:

    `<a-z>

quick jump between marks:

    ``

jump to last modified line:

    `.

show all marks:

    :mark

---
###_find_###
---

count how many matches:

    :%s/pattern//n


---
###_miscellaneous_###
---

this can be used in `#include` files etc.

on the file name, press `gf` to "go to file", `Ctrl+o` to go back to the previous file. `Ctrl+6` also works.

Unhighlight serach

    :noh


on top of a number `ctrl+a` to increase it, `ctrl+x` to decrease it.


when in `insert mode`, `ctrl+c` will exit to normal mode, it will not kill vim.
