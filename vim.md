##vim related##
---
###_shortcuts_###

    :sp filename

open `filename` in a split window.

Another way is `Ctrl+w+v`  then do:

    :e filename

Note that `<tab>` works under this option.

`%` shortcur for jumping between matching brackets.

`#` and `*` find previous and next identifier.

`(` and `)` move around by _sentences_.

`{` and `}` move around by _paragraph_.


`[[`, `]]` move to previous and next function.

`>>`,`<<` are used to indent and unindent line.

`yy` to copy, and `dd` to delete. 

the difference beteween `0` and `^` is that `^` moves to the first non-white character. 

`$` moves to the last character.

`Ctrl+w+v` split window vertically.

`number` then `|`: goto colums

convert `<eol>`: `:set fileformat=unix` then `:w`


    vimdiff <file1> <file2>


toggle whitespace:

    :set list!

