##sed awk and grep related##

this is some advance topic: still working on it.

###sed###

    sed '' input.txt

    sed '/searchTerm/a \
    insert this after searchTerm' input.txt

    sed '$ i\
    addToLastLine' input.txt

use sed like grep:

    git log -3|sed -n '/Date/p'

note `git log -3|sed -n'/Date/p'` is wrong, must have `space` between `-n` and `''`.

this is a more interesting example:

    git log -3|sed -n '/Date/{n;n;p}'

print two lines after the line that matches 'Date'.

###awk###

example:

    ll|awk '{print $3, "owns",$9}'

|pre-defined variable|meaning|
|---|------|
|FS|Field Separator|
|RS|Record Separator (lines)|
|OFS|Output Field Separator|
|ORS|Output Record Separator|

awk -f my_script.awk filename

###grep###

grep version of the previous example:

    git log -3|grep Date -A 3 -B 1


`-A` afterward context, `-B` previous context.