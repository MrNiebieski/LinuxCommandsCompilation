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
    cd

go to last folder:
    cd -

cp: copy folder to current location:

    cp -r /home/foler1/ .

NOTE: `cp` and `mv` will overwrite if target exists.

check Disk Usage:

    du
    du -h
    du -ah
    du -sh

`-h` for human-readable `-a` for all files.

`-S` qdo not include size of subdirectories.

produce short result

    du -sh --time

advanced `mkdir`

    mkdirhier project/{lib/ext,bin,src,doc/{html,info,pdf},demo/stat/a}
    cd tmp/a/b/c || mkdir -p tmp/a/b/c && tar xvf -C tmp/a/b/c ~/archive.tar


---
###_chmod_###
---

2 ways of using `chmod`

    chmod 777
    chmod a+r

options for "who it applies to" `u` user, `g` group, `o` others `a` all.

`+` add permissions, `-` subtract permissions, `=` set permissions.

`r` read, `w` write, `x` excute.

for example `600` is a very conservative mode. `777` is very loose.

---
###_find_###
---

_TODO: this section needs to be expanded_

    find some-file-criteria some-file-path

    find /user -name "*.txt"
    find /usr -size +10M
    find /usr -mtime +120
    find *.*  -mtime -0.05
    find /usr /var \! -atime -90

`-mtime` is for modified, `-atime` is for accessed, unit is days.

to use with `xargs`

    find . -name "*.c" | xargs rm -rf

However, if there is `space` in filename.

    find . -name "*.c" -print0 | xargs -0 rm -rf



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
    lscpu

system:

    uname -a
    arch

mount & unmount

    sudo mkdir /mnt/usb
    sudo mount /dev/sda /mnt/usb
    df -h
    udisk --unmount /dev/sda
    udisk --eject /dev/sda
    mount|column -t

show disk partition:

    sudo fdisk -l
    cat /proc/partitions

---
###_process management_###
---
show currently active processes, with their pid

    ps

kill a process:

    kill <pid>
    kill -9 <pid>

    top

suspend and resume:

    [Ctrl+] Z
    fg
    

---
###_user management_###
---

check logged on users:

    w

check if there is a user name XX in this computer

    grep XX /etc/passwd

list user with `awk`:

    awk -F: '{print $1,$3,$6}' /etc/passwd

---
###_pipes_###
---

    a > b

Redirect a's standard output to overwrite file b

    a >> b

Redirect a's standard output to append to the file b

    a &> b

Redirect a's error output to overwrite file b

    a < b

Redirect a's standard input to read from the file b

    a | b

Redirect a's standard output to b's standard input



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

`Ctrl+l` clear the terminal.

`Ctrl+d` logout.

`PgUp` and `PgDn` in a terminal will scroll through commands, to actually scroll through terminal, use `shift+PgUp`, `shift+PgDown`. 

---
###_start up setting_###
---
To switch betwen GUI mode and text mode (CentOS, RedHat), `sudo vim /etc/inittab`

Text:
    id:3:initdefault:

GUI:
    id:5:initdefault:

to check runlevel:

    who -r

---
###_shutting down_###
---

    sudo shutdown -h now
    sudo halt
    sudo halt -p
    sudo poweroff

---
###_pager_###
---

show certain lines of a file

    sed -n '10, 15p' filename


---
###_miscellaneous_###
---

Run the lines in the file as if they were typed to the shell.

    source file

Run `program` in the background:

    program &

to run a couple of commands in sudo:

    sudo bash


SSH key pair generation

    ssh-keygen

show file name including full path name:

    `readlink -f <file.txt>`

show 3 months' calendar

    cal -3

easiest way to create an empty file:

    >tmp.txt

`-e` after echo is to enable backlash `\`

    echo -e "1d\n2d\n5d" > commands.txt