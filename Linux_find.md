find files written in the last 2 days to your home dir:

find /home/*/ -type f -mtime -2 

Find php files older than 5 days:

find /var/www/html -type f -name ‘*.php’ -mtime +5 

files modified between specific times:

find . -newermt "2020-12-01 00:00:00" ! -newermt "2020-12-02 00:00:00" 

