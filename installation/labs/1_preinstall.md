#Preinstall

##1.- Configuración de SWAP

```sh
[root@elephant ~]# sysctl -w vm.swappiness=1
vm.swappiness =1 
```
*Como este cambio es temporal, se edita el archivo /etc/sysctl.conf añadiendo la linea

```sh
vm.swappiness = 1
```

Verificamos el cambio esta aplicado

```sh
[root@elephant ~]# sysctl -a | grep swapp 
vm.swappiness = 1
```
##2,3.- Atributos de Volumenes

```sh
[root@elephant ~]# lsblk -fs
NAME   FSTYPE LABEL UUID                                 MOUNTPOINT
xvda1                                                    
└─xvda                                                   
xvda2  xfs          de4def96-ff72-4eb9-ad5e-0847257d1866 /
└─xvda                                                   
xvdb   ext4         ba2a8bba-5f2b-4c82-9404-6bf819b10aef /data/disk0
xvdc   ext4         68edb13b-beb2-4ba1-8cee-8ccffcf2295c /data/disk1
```

##4.- Deshabilitando Transparent HugePages (THP)
```sh
[root@elephant ~]# cat /sys/kernel/mm/transparent_hugepage/enabled
[always] madvise never
[root@elephant ~]# vim /etc/rc.local
--Agregamos
if test -f /sys/kernel/mm/transparent_hugepage/enabled; then
   echo never > /sys/kernel/mm/transparent_hugepage/enabled
   echo never > /sys/kernel/mm/transparent_hugepage/defrag
fi
```

Validamos
```sh
[root@elephant ~]# cat /sys/kernel/mm/transparent_hugepage/enabled
always madvise [never]
[root@elephant ~]# cat /sys/kernel/mm/transparent_hugepage/defrag
always madvise [never]
```
##5.- Configuracion de Red
```sh
ifconfig
eth0: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 9001
        inet 172.31.37.197  netmask 255.255.240.0  broadcast 172.31.47.255
        ether 0e:c4:0e:9b:c4:9a  txqueuelen 1000  (Ethernet)
        RX packets 9923  bytes 985245 (962.1 KiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 10221  bytes 1182669 (1.1 MiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

lo: flags=73<UP,LOOPBACK,RUNNING>  mtu 65536
        inet 127.0.0.1  netmask 255.0.0.0
        loop  txqueuelen 1  (Local Loopback)
        RX packets 157  bytes 20136 (19.6 KiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 157  bytes 20136 (19.6 KiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0
```

##6.- Reverse host lookups 
```sh
[hduser@elephant ~]$ getent hosts $(hostname -a)
127.0.0.1       localhost localhost.localdomain localhost4 localhost4.localdomain4
127.0.0.1       localhost localhost.localdomain localhost6 localhost6.localdomain6
172.31.37.197   elephant
172.31.46.216   horse
172.31.33.162   tiger
172.31.35.136   lion
172.31.45.253   monkey
```
##7.- nscd en ejecución
```sh
systemctl status nscd
● nscd.service - Name Service Cache Daemon
   Loaded: loaded (/usr/lib/systemd/system/nscd.service; disabled; vendor preset: disabled)
   Active: active (running) since lun 2017-11-27 13:50:50 CST; 2s ago
  Process: 12420 ExecStart=/usr/sbin/nscd $NSCD_OPTIONS (code=exited, status=0/SUCCESS)
 Main PID: 12421 (nscd)
   CGroup: /system.slice/nscd.service
           └─12421 /usr/sbin/nscd

nov 27 13:50:50 elephant.vinkos nscd[12421]: 12421 monitoring file `/etc/hosts` (4)
nov 27 13:50:50 elephant.vinkos nscd[12421]: 12421 monitoring directory `/etc` (2)
nov 27 13:50:50 elephant.vinkos nscd[12421]: 12421 monitoring file `/etc/resolv.conf` (5)
nov 27 13:50:50 elephant.vinkos nscd[12421]: 12421 monitoring directory `/etc` (2)
nov 27 13:50:50 elephant.vinkos nscd[12421]: 12421 monitoring file `/etc/services` (6)
nov 27 13:50:50 elephant.vinkos nscd[12421]: 12421 monitoring directory `/etc` (2)
nov 27 13:50:50 elephant.vinkos nscd[12421]: 12421 disabled inotify-based monitoring for file `/etc/netgroup': No such file or directory
nov 27 13:50:50 elephant.vinkos nscd[12421]: 12421 stat failed for file `/etc/netgroup'; will try again later: No such file or directory
nov 27 13:50:50 elephant.vinkos nscd[12421]: 12421 Access Vector Cache (AVC) started
nov 27 13:50:50 elephant.vinkos systemd[1]: Started Name Service Cache Daemon.
```
##8.- ntpd en ejecución
```sh
systemctl status ntpd
● ntpd.service - Network Time Service
   Loaded: loaded (/usr/lib/systemd/system/ntpd.service; enabled; vendor preset: disabled)
   Active: active (running) since lun 2017-11-27 13:52:37 CST; 2s ago
  Process: 12453 ExecStart=/usr/sbin/ntpd -u ntp:ntp $OPTIONS (code=exited, status=0/SUCCESS)
 Main PID: 12454 (ntpd)
   CGroup: /system.slice/ntpd.service
           └─12454 /usr/sbin/ntpd -u ntp:ntp -g

nov 27 13:52:37 elephant.vinkos ntpd[12454]: proto: precision = 0.258 usec
nov 27 13:52:37 elephant.vinkos ntpd[12454]: 0.0.0.0 c01d 0d kern kernel time sync enabled
nov 27 13:52:37 elephant.vinkos ntpd[12454]: ntp_io: estimated max descriptors: 1024, initial socket boundary: 16
nov 27 13:52:37 elephant.vinkos ntpd[12454]: Listen and drop on 0 v4wildcard 0.0.0.0 UDP 123
nov 27 13:52:37 elephant.vinkos ntpd[12454]: Listen and drop on 1 v6wildcard :: UDP 123
nov 27 13:52:37 elephant.vinkos ntpd[12454]: Listen normally on 2 lo 127.0.0.1 UDP 123
nov 27 13:52:37 elephant.vinkos ntpd[12454]: Listen normally on 3 eth0 172.31.37.197 UDP 123
nov 27 13:52:37 elephant.vinkos ntpd[12454]: Listening on routing socket on fd #20 for interface updates
nov 27 13:52:37 elephant.vinkos ntpd[12454]: 0.0.0.0 c016 06 restart
nov 27 13:52:37 elephant.vinkos ntpd[12454]: 0.0.0.0 c012 02 freq_set kernel 61.964 PPM
```

##Deshabilitando el chrony, tuned y firewalld

Validamos el estatus actual

```sh
[root@elephant ~]# systemctl status chronyd
● chronyd.service - NTP client/server
   Loaded: loaded (/usr/lib/systemd/system/chronyd.service; enabled; vendor preset: enabled)
   Active: active (running) since lun 2017-11-27 09:51:12 CST; 3h 3min ago
     Docs: man:chronyd(8)
           man:chrony.conf(5)
  Process: 656 ExecStartPost=/usr/libexec/chrony-helper update-daemon (code=exited, status=0/SUCCESS)
  Process: 639 ExecStart=/usr/sbin/chronyd $OPTIONS (code=exited, status=0/SUCCESS)
 Main PID: 644 (chronyd)
   CGroup: /system.slice/chronyd.service
           └─644 /usr/sbin/chronyd

nov 27 09:51:12 elephant.vinkos systemd[1]: Starting NTP client/server...
nov 27 09:51:12 elephant.vinkos chronyd[644]: chronyd version 3.1 starting (+CMDMON +NTP +REFCLOCK +RTC +PRIVDROP +SCFILTER +SECHASH +SIGND +ASYNCDNS +IPV6 +DEBUG)
nov 27 09:51:12 elephant.vinkos chronyd[644]: Frequency 40.093 +/- 0.066 ppm read from /var/lib/chrony/drift
nov 27 09:51:12 elephant.vinkos systemd[1]: Started NTP client/server.
nov 27 09:51:17 elephant.vinkos chronyd[644]: Selected source 173.230.144.109
nov 27 09:51:21 elephant.vinkos chronyd[644]: Selected source 45.55.217.50
[root@elephant ~]# systemctl status | grep -e tune -e ktune
           │   │ └─11527 grep --color=auto -e tune -e ktune
             ├─tuned.service
             │ └─884 /usr/bin/python -Es /usr/sbin/tuned -l -P
[root@elephant ~]# systemctl status frewalld
Unit frewalld.service could not be found.
```

Detenemos los servicios activos

```sh
[root@elephant ~]# systemctl stop chronyd
[root@elephant ~]# systemctl disable chronyd
Removed symlink /etc/systemd/system/multi-user.target.wants/chronyd.service.
[root@elephant ~]# systemctl status chronyd
● chronyd.service - NTP client/server
   Loaded: loaded (/usr/lib/systemd/system/chronyd.service; disabled; vendor preset: enabled)
   Active: inactive (dead)
     Docs: man:chronyd(8)
           man:chrony.conf(5)

nov 27 09:51:12 elephant.vinkos systemd[1]: Starting NTP client/server...
nov 27 09:51:12 elephant.vinkos chronyd[644]: chronyd version 3.1 starting (+CMDMON +NTP +REFCLOCK +RTC +PRIVDROP +SCFILTER +SECHASH +SIGND +ASYNCDNS +IPV6 +DEBUG)
nov 27 09:51:12 elephant.vinkos chronyd[644]: Frequency 40.093 +/- 0.066 ppm read from /var/lib/chrony/drift
nov 27 09:51:12 elephant.vinkos systemd[1]: Started NTP client/server.
nov 27 09:51:17 elephant.vinkos chronyd[644]: Selected source 173.230.144.109
nov 27 09:51:21 elephant.vinkos chronyd[644]: Selected source 45.55.217.50
nov 27 12:57:50 elephant.vinkos systemd[1]: Stopping NTP client/server...
nov 27 12:57:50 elephant.vinkos chronyd[644]: chronyd exiting
nov 27 12:57:50 elephant.vinkos systemd[1]: Stopped NTP client/server.
[root@elephant ~]# tuned-adm off
[root@elephant ~]# tuned-adm list
Available profiles:
- balanced                    - General non-specialized tuned profile
- desktop                     - Optimize for the desktop use-case
- latency-performance         - Optimize for deterministic performance at the cost of increased power consumption
- network-latency             - Optimize for deterministic performance at the cost of increased power consumption, focused on low latency network performance
- network-throughput          - Optimize for streaming network throughput, generally only necessary on older CPUs or 40G+ networks
- powersave                   - Optimize for low power consumption
- throughput-performance      - Broadly applicable tuning that provides excellent performance across a variety of common server workloads
- virtual-guest               - Optimize for running inside a virtual guest
- virtual-host                - Optimize for running KVM guests
No current active profile.
[root@elephant ~]# systemctl stop tuned
[root@elephant ~]# systemctl disable tuned
Removed symlink /etc/systemd/system/multi-user.target.wants/tuned.service.
[root@elephant ~]# systemctl status tuned
● tuned.service - Dynamic System Tuning Daemon
   Loaded: loaded (/usr/lib/systemd/system/tuned.service; disabled; vendor preset: enabled)
   Active: inactive (dead)

nov 27 09:51:13 elephant.vinkos systemd[1]: Starting Dynamic System Tuning Daemon...
nov 27 09:51:13 elephant.vinkos systemd[1]: Started Dynamic System Tuning Daemon.
nov 27 12:59:17 elephant.vinkos systemd[1]: Stopping Dynamic System Tuning Daemon...
nov 27 12:59:17 elephant.vinkos systemd[1]: Stopped Dynamic System Tuning Daemon.
```


