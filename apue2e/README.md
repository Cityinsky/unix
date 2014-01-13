Instructons on CentOS
----------------------

There probably will be some errors occur when you excuting make. Here are some
common ones:

1. 'error: stropts.h: No such file or directory'


  Solution:

    shell> cd /tmp/
    shell> wget http://ftp.gnu.org/gnu/libc/glibc-2.11.tar.gz
    shell> tar xzvf glibc-2.11.tar.gz
    shell> cp ./glibc-2.11/streams/stropts.h /usr/include
    shell> cp ./glibc-2.11/bits/stropts.h /usr/include/bits
    shell> cp ./glibc-2.11/sysdeps/x86_64/bits/xtitypes.h /usr/include/bits

2. error: 'ARG_MAX' undeclared here

  Solution:

    - Add the following line to apue.2e/include/apue.h

        #define ARG_MAX 4096

    - Add the following line to apue.2e/threadctl/getenv1.c and apue.2e/threadctl/getenv3.c

        #include "apue.h"
