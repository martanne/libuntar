libuntar - C library for extracting tar files
======

libuntar is a library for manipulating tar files from within C programs.

It is based on libtar from http://repo.or.cz/w/libtar.git

The idea was to remove all code for creating and appending to tarfiles,
add tests, and remove all support for obsolete platforms, and simplify
the build process, so there is just a very minimal library to extract
tar files, optionally with decompression.

The library is currently just under 10k on amd64.

It requires Linux, NetBSD 7, OpenBSD. FreeBSD is missing utimensat(2)
so not curently working (please fix FreeBSD!).

Current build instructions:
```
   set CFLAGS, LDFLAGS if required
   make
```
There is an example untar program using the library.

Compile time options:
   -DUSE\_SYMBOLIC\_IDS use symbolic names from tarfiles, default is numeric
   -DDEBUG verbose debug
   -DHAVE\_LIBZ for untar, use libz
