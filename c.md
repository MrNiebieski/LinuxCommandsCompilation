##C/C++ related##
---
###_makefile_###
---
if the makefile does not have default name like makefile or Makefile, it is possible to specify the filename like the following:

    make -f Makefile2
    #OR
    make --file=Makefile2

PHONY: (avoid conflicting with exsiting files)

    .PHONY: clean
    clean: *.o

`@` is used to turn off echoing.

wildcard useage is tha same as bash.

`%` is used to do 'grep-like' matching.

`=` i s used to define variables. Advanced variations are `:=`, `?=`, `+=`.

`?=` if it doesn't have a value, set it.

`+=` append

`$(VARIABLE)` and `${VARIABLE}` are equivalent in referring to variables.

`$$` for environmental variable

    test:
        @echo $$HOME

*Automatic Vairables*

    target: dependency1 dependency2

1. `$@`: current Target

   `(@D)`, `(@F)`: current Directory and File

2. `$<`: dependency1

   `$(<D)`, `$(<F)`: dependency1 Directory and File

3. `$^`: all dependencies

4. `$*`: captured by `%`

5. `$?`: dependencies that is newer than target


---
###_makefile in C compiling_###
---

`CXX, CXXFLAGS` is related to c++ compiler `g++`, `CPP, CPPFLAGS`is related to pre processor (not c plus plus).

`CC, CFLAGS` is for c compiler `cc`.

`-I` in `CFLAGS` is to set to include non-standard directories.

`LDFLAGS` if for the linker, `-l` is for specific library files and `-L` is the library search path.

---
###_gcc_###
---

gcc optinos:

1. `-g`: extra debugging info
2. `-o`: file output should be named file
3. `-c`: compile without linking


---
###_gdb_###
---
gdb options

|command line|effect|
|------------|------|
|r|run|
|l|list|

---
###_valgrind_###
--- 

track errors like:

1. uninitialized variable
2. memory leak
3. buffer overflow

does not detect:

1. static memory errors
2. if the error does not occur during runtime 


---
###_ctags_###
---

to setup:

    ctags -R

`ctrl+]` and `ctrl+t` to go into a function and go back.