libkqueue
=========

A user space implementation of the kqueue(2) kernel event notification mechanism
libkqueue acts as a translator between the kevent structure and the native
kernel facilities on Linux, Android, Solaris, and Windows.

Supported Event Types
---------------------

* vnode
* socket
* proc
* user
* timer

Installation - Linux, Solaris
-----------------------------

    cmake -G "Unix Makefiles" -DCMAKE_INSTALL_PREFIX=/usr -DCMAKE_INSTALL_LIBDIR=lib <path to source>
    make
    make install

Installation - Red Hat
----------------------

    cmake -G "Unix Makefiles" -DCMAKE_INSTALL_PREFIX=/usr -DCMAKE_INSTALL_LIBDIR=lib <path to source>
    make
    cpack -G RPM

Installation - Debian
---------------------

    cmake -G "Unix Makefiles" -DCMAKE_INSTALL_PREFIX=/usr -DCMAKE_INSTALL_LIBDIR=lib <path to source>
    make
    cpack -G DEB

Installation - Android
----------------------

    cmake -G "Unix Makefiles" -DCMAKE_C_COMPILER=<path to NDK compiler> -DCMAKE_INSTALL_PREFIX=/usr -DCMAKE_INSTALL_LIBDIR=lib <path to source>
    make

Windows (Visual Studio Project)
-------------------------------

    cmake -G "Visual Studio 14 2015" <path to source>
    cmake --build .

Windows (clang/C2) (Visual Studio Project)
------------------------------------------

    cmake -G "Visual Studio 14 2015" -T "LLVM-vs2014" <path to source>
    cmake --build .

Xcode (project)
---------------

    cmake -G "Xcode" <path to source>

Running Unit Tests
------------------

    cmake -G "Unix Makefiles" -DCMAKE_INSTALL_PREFIX=/usr -DCMAKE_INSTALL_LIBDIR=lib -DENABLE_TESTING=YES <path to source>
    make
    make test

Building Applications
---------------------

    CFLAGS += -I/usr/include/kqueue
    LDFLAGS += -lkqueue

Tutorials & Examples
--------------------

[Kqueues for Fun and Profit](http://doc.geoffgarside.co.uk/kqueue)

[Handling TCP Connections with Kqueue Event Notification](http://eradman.com/posts//kqueue-tcp.html)

Releases History
----------------

2.0 add support for Android _2013-04-29_

1.0 stable relesae for Linux, Solaris, and Windows _2010-09-18_
