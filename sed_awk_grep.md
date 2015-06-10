##sed awk and grep related##

this is some advance topic: still working on it.

###sed###

    sed '' input.txt

    sed '/searchTerm/a \
    insert this after searchTerm' input.txt

    sed '$ i\
    addToLastLine' input.txt


    sed -f commands.txt input.txt

use sed like grep:

    git log -3|sed -n '/Date/p'

note `git log -3|sed -n'/Date/p'` is wrong, must have `space` between `-n` and `''`.

this is a more interesting example:

    git log -3|sed -n '/Date/{n;n;p}'

print two lines after the line that matches 'Date'.

in sed, comma `,` is a range operator.

can be used together with regular expression match

    sed '/Storm/,/Fellowship/d' books.txt

`w` write command:

    sed -n -e '/Martin/ w Martin.txt' -e '/Paulo/ w Paulo.txt' -e '/Tolkien/ w 
    Tolkien.txt' books.txt

`c` change; `i`, insert;

###awk###

example:

    ll|awk '{print $3, "owns",$9}'

|pre-defined variable|meaning|
|---|------|
|FS|Field Separator|
|RS|Record Separator (lines)|
|OFS|Output Field Separator|
|ORS|Output Record Separator|
|FILENAME|file name|

    awk -f my_script.awk filename

    awk 'length($0) > 18' marks.txt

###grep###

grep version of the previous example:

    git log -3|grep Date -A 3 -B 1


`-A` afterward context, `-B` previous context.


`--no-filename` is an option.

`-c` takes counts