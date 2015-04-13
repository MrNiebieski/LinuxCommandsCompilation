#linux:#

---
###_file system_###
---
ls variations:

    ll
    ls -al
    ls -thor

`al` list hidden file, `ll` is short, (not supported by every version of linux), `thor` because of this is funny.

---
###_system info_###
---
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
`ESC+.` last argument

combo:

`Ctrl+u`, `Ctrl+y`, from cusor to begining, copy and paste

to copy the whole line but the cursor is not at the end of the line, press `Ctrl+e` first.

Similarly press `Ctrl+a` moves cursor to the begining of the line.

`Ctrl+w` will cut "word" from cursor to the left, stop at blank space, etc.
`Ctrl+k` will cut from cursor to the end.

Therefore, to delete a line line while the cursor is somewhere in the middle

    Ctrl+(u then k)

