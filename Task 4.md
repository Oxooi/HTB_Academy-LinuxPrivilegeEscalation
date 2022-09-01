# IP :
> 10.129.245.178

# CMD Use :
> find / -user root -perm -4000 -exec ls -ldb {} \; 2>/dev/null (SETUID)
> find / -user root -perm -6000 -exec ls -ldb {} \; 2>/dev/null (GETUID)