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

`ctrl+shift+g` show filename and line.

`ctrl+shift+u`, `ctrl+shift+d` moves down and up by half a screen.

`ctrl+shift+f`, `ctrl+shift+b` moves down and up by one screen.

`z` then `enter`, move current line to the top of the screen.

`H` moves to the first line on the screen. 

`O` begin a new line above the curosr and enter insert mode. `o` is below the cursor.

`%` shortcur for jumping between matching brackets.

`#` and `*` find previous and next identifier.

`(` and `)` move around by _sentences_.

`{` and `}` move around by _paragraph_.


`[[`, `]]` move to previous and next function.

`>>`,`<<` are used to indent and unindent line.

`==` auto indentation.

`yy` or `Y` to copy, and `dd` to delete. 

the difference beteween `0` and `^` is that `^` moves to the first non-white character. 

`$` moves to the last character.

`Ctrl+w+v` split window vertically.

`number` then `|`: goto colums.

`f<c>` moves _within_ a line to the next `c` character.

convert `<eol>`: `:set fileformat=unix` then `:w`


    vimdiff <file1> <file2>


toggle whitespace:

    :set list!


replace single character:

    r<c>

`:cope` after `:make` to navigate around error and warnings.
`:cn`,`:cp` to move around.
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

show all marks:

    :mark

---
###_find_###
---

count how many matches:

    :%s/pattern//n
