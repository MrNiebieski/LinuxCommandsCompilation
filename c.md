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

---
###_gdb_###
---
gdb options

|command line|effect|
|------------|------|
|r|run|
|l|list|


---
###_gcc_###
---

gcc optinos:

1. `-g`: extra debugging info
2. `-o`: file output should be named file
3. `-c`: compile without linking 
