List the process information:
ps -auxf 

To find when the process started, you can use this command:
ps -eo lstart,pid,user,args --sort=start_time 

If you see a PID with content, it may be worth further investigation:
ps auxf |grep '\[' |awk '{print $2}' |xargs -I % sh -c 'echo PID: %; strings /proc/%/maps' 2> /dev/null 

allows you to see in /proc
lsof -p (pid)




