# Hacked-System-Diagnostic-Solution

#### List Current Logged-In User
$w or $who
#### List Last Logged-In Users
$last
#### List Last 200 lines of Commands for Current User
$cat ~/.bash_history | less
$vi /home/username/.bash_history
#### List System File Changed Recently
$find /etc /var -mtime -2
```
-2 means 2 days; the sample will show the last 2 days
```
#### List Active Connections
```
LISTEN - waiting for connection
ESTABLISHED - have a connection open
```
$netstat | less
#### Show the IP of Active Users When Communicating
$netstat -atnp | grep ESTA
#### Check connected IP and Opened connection in each IP
$netstat -ntu|awk '{print $5}'|cut -d: -f1 -s|sort|uniq -c|sort -nk1 -r
#### List all networked Processes
lsof -i
#### Call All System calls made by Process
$strace -d -p <PID Number>
#### Show Users Process
$ps aux
```
  a - show process for all users
  u - display the process user/owner
  x - show process not attached to terminal
```
#### Check Running Process
$top
$htop
#### Check SSH Attempt Connection
$tail -n 300 /var/log/auth.log
$tail -n 300 /var/log/auth.log | grep sshd
#### Check Open Ports
$nmap localhost
#### Kernel Data Structure
$ls /proc/*/exe -la
#### Common Attack Points
$ls /tmp -la
$ls /dev/shm -la
$ls /var/tmp -la
```
Common unsecured places
```
#### Show Crontab Scheduled Jobs
$less /etc/crontab
#### View Specific Software Cronjobs
$cd /etc/cron.d/
$ls -l
#### Listing Users Cronjobs When using Systemd timers
$systemctl list-timers


