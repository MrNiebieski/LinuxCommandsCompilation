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

`:=` expansion is done immediately, can be used in the begining of the file, followed by empty. All the following will be appended by `+=`.


`$(VARIABLE)` and `${VARIABLE}` are equivalent in referring to variables.

`$$` for environmental variable

    test:
        @echo $$HOME

Example for checking system:

    OSUPPER = $(shell uname -s 2>/dev/null | tr "[:lower:]" "[:upper:]")
    OSLOWER = $(shell uname -s 2>/dev/null | tr "[:upper:]" "[:lower:]")

    OS_SIZE    = $(shell uname -m | sed -e "s/x86_64/64/" -e "s/armv7l/32/" -e "s/aarch64/64/")
    OS_ARCH    = $(shell uname -m)
    ARCH_FLAGS =

    DARWIN = $(strip $(findstring DARWIN, $(OSUPPER)))
    ifneq ($(DARWIN),)
        XCODE_GE_5 = $(shell expr `xcodebuild -version | grep -i xcode | awk '{print $$2}' | cut -d'.' -f1` \>= 5)
    endif

    # Take command line flags that override any of these settings
    ifeq ($(x86_64),1)
        OS_SIZE = 64
        OS_ARCH = x86_64
    endif
    ifeq ($(ARMv7),1)
        OS_SIZE    = 32
        OS_ARCH    = armv7l
        ARCH_FLAGS = -target-cpu-arch ARM
    endif
    ifeq ($(aarch64),1)
        OS_SIZE    = 64
        OS_ARCH    = aarch64
        ARCH_FLAGS = -target-cpu-arch ARM
    endif    

*Automatic Vairables*

    target: dependency1 dependency2

1. `$@`: current Target

   `(@D)`, `(@F)`: current Directory and File

2. `$<`: dependency1

   `$(<D)`, `$(<F)`: dependency1 Directory and File

3. `$^`: all dependencies

4. `$*`: captured by `%`

5. `$?`: dependencies that is newer than target


example:

    %.o: %.cpp
        $(CXX) $(CPPFLAGS) $(LDFLAGS) -o $@ -c $< $(LIBS)

or:

        $(CXX) $(CPPFLAGS) $(LDFLAGS) -o $@ $^ $(LIBS)

search for `.h` file:

    find /usr/ -name "*.h" |grep host


---
###_makefile in C compiling_###
---

`CXX, CXXFLAGS` is related to c++ compiler `g++`, `CPP, CPPFLAGS`is related to pre processor (not c plus plus).

`CC, CFLAGS` is for c compiler `cc`.

`-I` in `CFLAGS` is to set to include non-standard directories.

`LDFLAGS` if for the linker, `-l` is for specific library files and `-L` is the library search path.


---
###_use cmake_###
---

typical usage:

    cmake .
    make


---
###_gcc_###
---

gcc optinos:

1. `-g`: extra debugging info
2. `-o`: file output should be named file
3. `-c`: compile without linking (output `.o` file)
4. `-O`, `-O2` turn on optimizations

disable dynamic-linked library.

    -static

opposite: use dynamic library as much as possible.

    -share

example:

    gcc file1.c fil2.c -o myprog

this is the same as:

    gcc -c file1.c
    gcc -c file2.c
    gcc file1.o file2.o -o myprog

show search path:

    gcc -v -E main.c > /dev/null
    gcc -H main.c

output this:

    COLLECT_GCC_OPTIONS='-v' '-E' '-mtune=generic'
     /usr/libexec/gcc/x86_64-redhat-linux/4.4.7/cc1 -E -quiet -v main.c -mtune=generic
    ignoring nonexistent directory "/usr/lib/gcc/x86_64-redhat-linux/4.4.7/include-fixed"
    ignoring nonexistent directory "/usr/lib/gcc/x86_64-redhat-linux/4.4.7/../../../../x86_64-redhat-linux/include"
    #include "..." search starts here:
    #include <...> search starts here:
     /usr/local/include
     /usr/lib/gcc/x86_64-redhat-linux/4.4.7/include
     /usr/include
    End of search list.

---
###_gdb_###
---

gdb need to be compiled by `gcc` with `-g` option.

gdb options:

|command line|effect|
|------------|------|
|r|run|
|l|list|
|q|quit|

print variable `a`:

    p <a>

add breakpoint at line 5:

    break <5>

add breakpoint at `function`:

    break <function>

show all breakpoints:

    info break

show assembly code:

    disas <functionName>

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
###_gprof_###
---

compile with `-pg` and run `gprof`, a `gmon.out` file will be generated.

---
###_ctags_###
---

to setup:

    ctags -R

`ctrl+]` and `ctrl+t` to go into a function and go back.

---
###_miscellaneous_###
---

`awk` trick statistics:

    ls -l  *.cpp *.c *.h | awk '{sum+=$5} END {print sum}'

or do this:

    wc -l *.cpp *.h

---
###_C/C++ programming_###
---

    whereis stdio.h
    whereis cuda.h

---
###_miscellaneous_###
---

to inspect object file: (to be elaborated later)

    ldd
    nm