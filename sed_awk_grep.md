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

###awk###