#linux:#

---
###_file system_###
---
ls variations:

    ll
    ls -al
    ls -thor

`al` list hidden file, `ll` is short, (not supported by every version of linux), `thor` because of this is funny.


cd variations:

go to home:
    cd ~

go to last folder:
    cd -

---
###_chmod_###
---

2 ways of using `chmod`

    chmod 777
    chmod a+r

options for "who it applies to" `u` user, `g` group, `o` others `a` all.

`+` add permissions, `-` subtract permissions, `=` set permissions.

`r` read, `w` write, `x` excute.

---
###_find_###
---

_TODO: this section needs to be expanded_


    find /user -name "*.txt"
    find /usr -size +10M
    find /usr -mtime +120
    find /usr /var \! -atime -90

`-mtime` is for modified, `-atime` is for accessed.

---
###_grep_###
---

example:

    grep stringYouWantToFind */*/*.php

recursive grep:

    grep -r stringYouWantToFind .
    grep -R stringYouWantToFind .

`-R` will folow symlinks. `.` is this directory, `"stringYouWantToFind"` must have `"` if there is spaces etc. in the string.

Or

    grep -r --include "*.php" stringYouWantToFind .

---
###_system info_###
---
`/proc` is a virtual filesystem that shows information of processes as files.

memory:

    free -g
    cat /proc/meminfo
    
CPU:

    cat /proc/cpuinfo


---
###_process management_###
---

    top

suspend and resume:

    [Ctrl+] Z
    fg
    

---
###_keyboard shortcut_###
---
`ESC+.` paste last argument

combo:

`Ctrl+u`, `Ctrl+y`, from cusor to begining, copy and paste

to copy the whole line but the cursor is not at the end of the line, press `Ctrl+e` first.

Similarly press `Ctrl+a` moves cursor to the begining of the line.

`Ctrl+w` will cut "word" from cursor to the left, stop at blank space, etc.
`Ctrl+k` will cut from cursor to the end.

Therefore, to delete a line line while the cursor is somewhere in the middle

    Ctrl+(u then k)

trick:

although using up/down arrow can browse through recent command, it's more efficient to use `Ctrl+r` then start typing the command, it will do a regex search on recent commands.

---
###_start up setting_###
---
To switch betwen GUI mode and text mode (CentOS, RedHat), `sudo vim /etc/inittab`

Text:
    id:3:initdefault:

GUI:
    id:5:initdefault: