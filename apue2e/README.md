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
        
        编译的过程中可能会出现的一个问题，也是一个网友曾经问到的问题，就是在编译中出现这个的错误，提示nawk command cannot be found。这个问题可能的原因是，有些操作系统的内核版本较低，可能还不支持nawk(new awk)这个命令。但应该支持awk命令。因此，问题的解决方法就是将相关文件中的nawk命令替换为awk，或者为系统添加一个别名alias，alias nawk awk。这样在编一的过程中，遇到nawk命令时，实际会去执行awk命令。
3
