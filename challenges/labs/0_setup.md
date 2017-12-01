# Challenge Setup

Create the Issue Challenges Setup
Make sure mfernest and rstokes/ronanstokes are Collaborators
Assign the Issue to yourself and label it started
In the file challenges/labs/0_setup.md:

## List the cloud provider you are using (AWS, GCE, Azure, CloudCat, other)

```sh
AWS
```

## List your instances by IP address and DNS name (don't use /etc/hosts for this)

```sh
[ec2-user@ip-172-31-20-143 ~]$ ifconfig
eth0: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 9001
        inet 172.31.20.143  netmask 255.255.240.0  broadcast 172.31.31.255
        inet6 fe80::8f9:17ff:fe79:15be  prefixlen 64  scopeid 0x20<link>
        ether 0a:f9:17:79:15:be  txqueuelen 1000  (Ethernet)
        RX packets 138758  bytes 179554613 (171.2 MiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 91003  bytes 6602399 (6.2 MiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

lo: flags=73<UP,LOOPBACK,RUNNING>  mtu 65536
        inet 127.0.0.1  netmask 255.0.0.0
        inet6 ::1  prefixlen 128  scopeid 0x10<host>
        loop  txqueuelen 1  (Local Loopback)
        RX packets 86  bytes 11434 (11.1 KiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 86  bytes 11434 (11.1 KiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

[ec2-user@ip-172-31-20-143 ~]$ hostname -f
ip-172-31-20-143.ec2.internal
[ec2-user@ip-172-31-17-0 ~]$ ifconfig
eth0: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 9001
        inet 172.31.17.0  netmask 255.255.240.0  broadcast 172.31.31.255
        inet6 fe80::814:3cff:fede:6380  prefixlen 64  scopeid 0x20<link>
        ether 0a:14:3c:de:63:80  txqueuelen 1000  (Ethernet)
        RX packets 5079  bytes 546830 (534.0 KiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 4170  bytes 559327 (546.2 KiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

lo: flags=73<UP,LOOPBACK,RUNNING>  mtu 65536
        inet 127.0.0.1  netmask 255.0.0.0
        inet6 ::1  prefixlen 128  scopeid 0x10<host>
        loop  txqueuelen 1  (Local Loopback)
        RX packets 86  bytes 11434 (11.1 KiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 86  bytes 11434 (11.1 KiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

[ec2-user@ip-172-31-17-0 ~]$ hostname -f
ip-172-31-17-0.ec2.internal
[ec2-user@ip-172-31-24-48 ~]$ ifconfig
eth0: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 9001
        inet 172.31.24.48  netmask 255.255.240.0  broadcast 172.31.31.255
        inet6 fe80::8e9:ddff:fe42:b950  prefixlen 64  scopeid 0x20<link>
        ether 0a:e9:dd:42:b9:50  txqueuelen 1000  (Ethernet)
        RX packets 5989  bytes 640901 (625.8 KiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 5178  bytes 789518 (771.0 KiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

lo: flags=73<UP,LOOPBACK,RUNNING>  mtu 65536
        inet 127.0.0.1  netmask 255.0.0.0
        inet6 ::1  prefixlen 128  scopeid 0x10<host>
        loop  txqueuelen 1  (Local Loopback)
        RX packets 57  bytes 9254 (9.0 KiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 57  bytes 9254 (9.0 KiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

[ec2-user@ip-172-31-24-48 ~]$ hostname -f
ip-172-31-24-48.ec2.internal
[ec2-user@ip-172-31-23-34 ~]$ ifconfig
eth0: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 9001
        inet 172.31.23.34  netmask 255.255.240.0  broadcast 172.31.31.255
        inet6 fe80::8c5:90ff:fedb:2388  prefixlen 64  scopeid 0x20<link>
        ether 0a:c5:90:db:23:88  txqueuelen 1000  (Ethernet)
        RX packets 4993  bytes 544769 (532.0 KiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 4129  bytes 554942 (541.9 KiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

lo: flags=73<UP,LOOPBACK,RUNNING>  mtu 65536
        inet 127.0.0.1  netmask 255.0.0.0
        inet6 ::1  prefixlen 128  scopeid 0x10<host>
        loop  txqueuelen 1  (Local Loopback)
        RX packets 57  bytes 9254 (9.0 KiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 57  bytes 9254 (9.0 KiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

[ec2-user@ip-172-31-23-34 ~]$ hostname -f
ip-172-31-23-34.ec2.internal
[ec2-user@ip-172-31-23-44 ~]$ ifconfig
eth0: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 9001
        inet 172.31.23.44  netmask 255.255.240.0  broadcast 172.31.31.255
        inet6 fe80::80a:e6ff:fecb:6a4c  prefixlen 64  scopeid 0x20<link>
        ether 0a:0a:e6:cb:6a:4c  txqueuelen 1000  (Ethernet)
        RX packets 4956  bytes 543980 (531.2 KiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 4145  bytes 559084 (545.9 KiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

lo: flags=73<UP,LOOPBACK,RUNNING>  mtu 65536
        inet 127.0.0.1  netmask 255.0.0.0
        inet6 ::1  prefixlen 128  scopeid 0x10<host>
        loop  txqueuelen 1  (Local Loopback)
        RX packets 59  bytes 9394 (9.1 KiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 59  bytes 9394 (9.1 KiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

[ec2-user@ip-172-31-23-44 ~]$ hostname -f
ip-172-31-23-44.ec2.internal
```

## List the Linux release you are using

```sh
[ec2-user@ip-172-31-20-143 ~]$ cat /etc/redhat-release
Red Hat Enterprise Linux Server release 7.4 (Maipo)
```

## List the file system capacity for the first node

```sh
[ec2-user@ip-172-31-20-143 ~]# df -h
S.ficheros     Tamaño Usados  Disp Uso% Montado en
/dev/xvda2        50G   1.1G   49G   3% /
devtmpfs          16G      0   16G   0% /dev
tmpfs             16G      0   16G   0% /dev/shm
tmpfs             16G    17M   16G   1% /run
tmpfs             16G      0   16G   0% /sys/fs/cgroup
tmpfs            3.2G      0  3.2G   0% /run/user/1000
/dev/xvdb         79G    57M   79G   1% /data/disk0
/dev/xvdc         79G    57M   79G   1% /data/disk1

```

## List the command and output for yum repolist enabled

```sh
[ec2-user@ip-172-31-20-143 ~]$ yum repolist enabled
Complementos cargados:amazon-id, rhui-lb, search-disabled-repos
Repo rhui-REGION-client-config-server-7 forced skip_if_unavailable=True due to: /etc/pki/rhui/cdn.redhat.com-chain.crt
Repo rhui-REGION-client-config-server-7 forced skip_if_unavailable=True due to: /etc/pki/rhui/product/rhui-client-config-server-7.crt
Repo rhui-REGION-client-config-server-7 forced skip_if_unavailable=True due to: /etc/pki/rhui/rhui-client-config-server-7.key
Repo rhui-REGION-rhel-server-releases forced skip_if_unavailable=True due to: /etc/pki/rhui/cdn.redhat.com-chain.crt
Repo rhui-REGION-rhel-server-releases forced skip_if_unavailable=True due to: /etc/pki/rhui/product/content-rhel7.crt
Repo rhui-REGION-rhel-server-releases forced skip_if_unavailable=True due to: /etc/pki/rhui/content-rhel7.key
Repo rhui-REGION-rhel-server-rh-common forced skip_if_unavailable=True due to: /etc/pki/rhui/cdn.redhat.com-chain.crt
Repo rhui-REGION-rhel-server-rh-common forced skip_if_unavailable=True due to: /etc/pki/rhui/product/content-rhel7.crt
Repo rhui-REGION-rhel-server-rh-common forced skip_if_unavailable=True due to: /etc/pki/rhui/content-rhel7.key
Could not contact CDS load balancer rhui2-cds01.us-east-1.aws.ce.redhat.com, trying others.
```

## Add the following Linux accounts to all nodes
User saturn with a UID of 2800
User haley with a UID of 2900
Create the group comets and add haley to it
Create the group planets and add saturn to it
```sh
[root@ip-172-31-20-143 ~]# useradd -u 2800 saturn
[root@ip-172-31-20-143 ~]# useradd -u 2900 haley
[root@ip-172-31-20-143 ~]# groupadd comets
[root@ip-172-31-20-143 ~]# groupadd planets
[root@ip-172-31-20-143 ~]# usermod -aG comets haley
[root@ip-172-31-20-143 ~]# usermod -aG planets saturn
```

## List the /etc/passwd entries for saturn and haley
Do not list the entire file

```sh
[root@ip-172-31-20-143 ~]# cat /etc/passwd | grep 'saturn\|haley'
saturn:x:2800:2800::/home/saturn:/bin/bash
haley:x:2900:2900::/home/haley:/bin/bash
```

##List the /etc/group entries for comets and planets
Do not list the entire file

```sh
[root@ip-172-31-20-143 ~]# cat /etc/group | grep 'comets\|planets'
comets:x:2901:haley
planets:x:2902:saturn

```

Push these updates to GitHub
Label your Issue review
Assign the Issue to the instructors
