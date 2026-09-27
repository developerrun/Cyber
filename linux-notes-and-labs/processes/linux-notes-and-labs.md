Linux Processes & Monitoring Study Notes
Processes

When a program is actively executing, using up system resources and not sitting ideally as passive code instructions in disk is referred as a process.

In linux , kernel initiates its own activities through processes calling the init program which tends to start system services.  Many of these processes are started as daemon programs (Programs which work in the background without any relation with user interface).

Ability of a process to start another process is called its parents process, which makes its further child processes. For every process there are unique process ID’s defined, so the kernel can easily navigate through the processes and keep track in memory.

$ ps
  PID TTY          TIME CMD
 1403 pts/0    00:00:00 zsh
 1556 pts/0    00:00:00 ps
```[cite: 2]

---

### Process `ps x`
The further option used to show all processes not only linked to current terminal is referred as `ps x`.

**Example Output:**
```bash
$ ps x
  PID TTY      STAT TIME COMMAND
  811 ?        Ss   0:00 /lib/systemd/systemd --user
  812 ?        S    0:00 (sd-pam)
  831 ?        S<sl 0:00 /usr/bin/pulseaudio --daemonize
  837 ?        Ssl  0:01 xfce4-session
  847 ?        Ss   0:01 /usr/bin/dbus-daemon --session
  878 ?        Ss   0:00 /usr/bin/ssh-agent x-session-ma
  888 ?        Ssl  0:01 /usr/libexec/at-spi-bus-launche
  893 ?        S    0:00 /usr/bin/dbus-daemon --config-f
  897 ?        Sl   0:00 /usr/lib/x86_64-linux-gnu/xfce4
  902 ?        Sl   0:00 /usr/lib/x86_64-linux-gnu/at-spi2-registryd
  911 ?        SLs  0:00 /usr/lib/x86_64-linux-gnu/gpg-agent --supervised
  913 ?        Sl   0:20 xfwm4 --display :0.0 --sm-clien
  916 ?        Ssl  0:00 /usr/libexec/gvfsd
  921 ?        Sl   0:00 /usr/libexec/gvfsd-fuse /run/us
  945 ?        Ssl  0:00 xfsettingsd --display :0.0 --sm
 1079 ?        Sl   0:02 xfce4-panel --display :0.0 --sm
 1135 ?        Sl   0:01 Thunar --sm-client-id 231516786
 1209 ?        Sl   0:02 xfdesktop --display :0.0 --sm-c
 1210 ?        Sl   0:00 /usr/lib/x86_64-linux-gnu/xfce4
 1215 ?        Sl   0:00 /usr/lib/x86_64-linux-gnu/xfce4
 1216 ?        Sl   0:00 /usr/lib/x86_64-linux-gnu/xfce4
 1217 ?        Sl   0:02 /usr/lib/x86_64-linux-gnu/xfce4
 1218 ?        Sl   0:00 /usr/lib/x86_64-linux-gnu/xfce4
 1219 ?        Sl   0:00 /usr/lib/x86_64-linux-gnu/xfce4
 1220 ?        Sl   0:00 /usr/lib/x86_64-linux-gnu/xfce4
 1237 ?        Ssl  0:00 /usr/libexec/gvfsd
 1241 ?        Ssl  0:00 xfce4-power-manager --restart -
 1242 ?        Sl   0:00 /usr/libexec/geoclue-2.0/demos/
 1246 ?        Sl   0:01 /usr/bin/python3 /usr/bin/bluem
 1256 ?        Sl   0:00 /usr/lib/policykit-1-gnome/polk
 1261 ?        Sl   0:00 light-locker
 1266 ?        Sl   0:00 /usr/lib/x86_64-linux-gnu/dconf-service
 1270 ?        Sl   0:00 nm-applet
```[cite: 2]

---

### Process States
Processes tends to have various states, which represents the stages a task goes from all the way from its creation to its completion:
* **Running:** Process is actively executing 
* **Sleeping:** Process is waiting for a particular event not running 
* **D:** Uninterruptible sleep, process waits for IO 
* **T:** Stopped 
* **Z:** A child process which has not yet been cleaned up by its parent 
* **<:** A high priority process, means it will get more CPU execution time. This property of the process is called niceness. A process is less nice as it gets more execution time 

Process states can be paired along with other characters:
* **(+)** -> Means that the process is directly tied to your terminal window and can accept inputs. 
* **(l)** -> This process will use multiple execution threads inside the same memory space. 
* **(N)** -> Low priority process that will yield extra CPU time for other processes to run faster. 

---

### Process `ps aux`
Another command that tends to display processes belonging to every user. It tends to show particular aspects of the process like its CPU consumption, USER ID and etc:
* **USER ID:** owner of process
* **CPU%:** Usage of Cpu shown in % 
* **% MEM:** Memory used by the process in percentage

**Example Output:**
```bash
$ ps aux
USER       PID %CPU %MEM    VSZ   RSS TTY STAT START   TIME COMMAND
root         1  0.1  0.2 168100 11396 ?   Ss   04:18   0:04 /sbin/init splash
root         2  0.0  0.0      0     0 ?   S    04:18   0:00 [kthreadd]
root         3  0.0  0.0      0     0 ?   I<   04:18   0:00 [rcu_gp]
root         4  0.0  0.0      0     0 ?   I<   04:18   0:00 [rcu_par_gp]
root         6  0.0  0.0      0     0 ?   I<   04:18   0:00 [kworker/0:0H-kblockd]
root         7  0.0  0.0      0     0 ?   I    04:18   0:00 [kworker/0:1-events]
root         9  0.0  0.0      0     0 ?   I<   04:18   0:00 [mm_percpu_wq]
root        10  0.0  0.0      0     0 ?   S    04:18   0:00 [ksoftirqd/0]
root        11  0.0  0.0      0     0 ?   I    04:18   0:01 [rcu_sched]
root        12  0.0  0.0      0     0 ?   S    04:18   0:00 [migration/0]
root        13  0.0  0.0      0     0 ?   S    04:18   0:00 [cpuhp/0]
root        14  0.0  0.0      0     0 ?   S    04:18   0:00 [cpuhp/1]
root        15  0.0  0.0      0     0 ?   S    04:18   0:00 [migration/1]
root        16  0.0  0.0      0     0 ?   S    04:18   0:00 [ksoftirqd/1]
root        18  0.0  0.0      0     0 ?   I<   04:18   0:00 [kworker/1:0H-kblockd]
root        19  0.0  0.0      0     0 ?   S    04:18   0:00 [cpuhp/2]
root        20  0.0  0.0      0     0 ?   S    04:18   0:00 [migration/2]
root        21  0.0  0.0      0     0 ?   S    04:18   0:01 [ksoftirqd/2]
root        23  0.0  0.0      0     0 ?   I<   04:18   0:00 [kworker/2:0H-kblockd]
```[cite: 3]

---

### Dynamic Viewing with `top`
`ps` command only tends to provide a snapshot of what the machine is doing at a particular instant. To have a more dynamic view of the processes executing we tend to use `top`.


top

1 top - 05:23:13 up  1:04,  1 user,  load average: 0.12, 0.08, 0.00
2 Tasks: 150 total,   1 running, 149 sleeping,   0 stopped,   0 zombie
3 %Cpu(s):  0.0 us,  0.6 sy,  0.0 ni, 99.4 id,  0.0 wa,  0.0 hi,  0.0 si,  0.0 st
4 MiB Mem :   3934.3 total,   2956.1 free,    496.8 used,     481.4 buff/cache
5 MiB Swap:    977.0 total,    977.0 free,      0.0 used.


1 Uptime & Load Average Line: Shows system uptime, number of active users, and load averages (indicating process demand over 1-, 5-, and 15-minute intervals).

2 Tasks Line: Shows the total number of tasks running and their states (running, sleeping, stopped, and zombie).

3 CPU Utilization (%Cpu(s)): Details how CPU time is distributed across user applications (us), system kernel (sy), idle time (id), and disk I/O wait (wa).

4 Physical Memory (MiB Mem): Tracks total, free, and used physical RAM, as well as buffer/cache memory allocated for file system optimization.

5 Swap Memory (MiB Swap): Monitors disk-backed virtual memory space used when physical RAM fills up.
.
