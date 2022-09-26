
# Do thr historical analysis 
Using sar you can monitor performance of various Linux subsystems (CPU, Memory, I/O..) in real time. You can also collect all performance data on an on-going basis, store them, and do historical analysis to identify bottlenecks.

sar Command Examples
1. Installing sar command:
a. To install sar command, you need to have “sysstat” package.

# yum install sysstat
# rpm -ivh sysstat-2.3.4
b. To configure the sar to retain logs of more than default 7 days.

# vi /etc/sysconfig/sysstat
Change the “HISTORY” parameter

2. CPU usage:
a. To get current CPU usage

# sar 2 10
# sar -p 2 10
# sar  -P ALL 2 10
b. To get the CPU usage for previous date, consider 14th:

# sar -P ALL -f /var/log/sa/sa14
c. To get the CPU usage for 10th of month, from 7 AM to 3 PM (i.e. with specifying the time):

# sar -P ALL -f /var/log/sa/sa10 -s 07:00:00 -e 15:00:00  
3. Memory usage:
a. To get current memory usage:

# sar -r 2 10
b. To get memory usage for previous date, consider 14th:

# sar -r -f /var/log/sa/sa14
c. To get memory usage for the 10th of month, from 7 AM to 3 PM (i.e. with specifying the time):

# sar -r -f /var/log/sa/sa10 -s 07:00:00 -e 15:00:00 
4. Swap usage:
a. To get current swap usage:

# sar -S 2 10
b. To get swap usage for previous date, consider 14th:

# sar -S -f /var/log/sa/sa14
c. To get swap usage for the 10th of month, from 7 AM to 3 PM:

# sar -S -f /var/log/sa/sa10 -s 07:00:00 -e 15:00:00 
5. Load Average:
a. To get current load average stats:

# sar -q 2 10
b. To get load average stats for previous date, consider 14th:

# sar -q -f /var/log/sa/sa14
c. To get load average stats for the 10th of month, from 7 AM to 3 PM:

# sar -q -f /var/log/sa/sa10 -s 07:00:00 -e 15:00:00 
6. Paging usage:
a. To get current paging usage:

# sar -B 2 10
b. To get paging usage for previous date, consider 14th:

# sar -B -f /var/log/sa/sa14
c. To get paging usage for the 10th of month, from 7 AM to 3 PM:

# sar -B -f /var/log/sa/sa10 -s 07:00:00 -e 15:00:00 
7. IO usage:
a. To get current IO usage:

# sar -b 2 10
b. To get IO usage for previous date, consider 14th:

# sar -b -f /var/log/sa/sa14
c. To get IO usage for the 10th of month, from 7 AM to 3 PM:

# sar -b -f /var/log/sa/sa10 -s 07:00:00 -e 15:00:00 
8. Disk IO usage:
a. To get current disk IO usage:

# sar -d -p 2 10
b. To get disk IO usage for previous date, consider 14th:

# sar -d -p -f /var/log/sa/sa14
c. To get disk IO usage for the 10th of month, from 7 AM to 3 PM:

# sar -d -p -f /var/log/sa/sa10 -s 07:00:00 -e 15:00:00 
9. Networking stats:
a. To get current network device stats:

# sar -n DEV 2 10
b. To get network device stats for previous date, consider 14th:

# sar -n DEV -f /var/log/sa/sa14
c. To get network device stats for the 10th of month, from 7 AM to 3 PM:

# sar -n DEV -f /var/log/sa/sa10 -s 07:00:00 -e 15:00:00
10. Power Management Stats:
a. To get current power management usage:

# sar -m 2 10
b. To get power management usage for previous date, consider 14th:

# sar -m -f /var/log/sa/sa14
c. To get power management usage for the 10th of month, from 7 AM to 3 PM:

# sar -m ALL -f /var/log/sa/sa10 -s 07:00:00 -e 15:00:00 
11. Memory Stats (Page activities):
a. To get current memory stats:

# sar -R 2 10
b. To get memory stats for previous date, consider 14th:

# sar -R -f /var/log/sa/sa14
c. To get memory stats for the 10th of month, from 7 AM to 3 PM:

# sar -R ALL -f /var/log/sa/sa10 -s 07:00:00 -e 15:00:00
Other Sysstat Utilities
Utility	Description
sar	It collects and displays ALL system activities statistics.
sadc	It stands for “system activity data collector”. This is the sar backend tool that does the data collection.
sa1	It stores system activities in binaryhttps://images-blogger-this purpose. sa1 runs from cron.
sa2	It creates daily summary of the collected statistics. sa2 runs from cron.
sadf	It can generate sar report in CSV, XML, and various other formats. Use this to integrate sar data with other tools.
iostat	It generates CPU, I/O statistics
mpstat	It displays CPU statistics.
pidstat	It reports statistics based on the process id (PID)
nfsiostat	It displays NFS I/O statistics.
cifsiostat	It generates CIFS statistics.
