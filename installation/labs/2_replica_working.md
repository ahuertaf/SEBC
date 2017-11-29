# Instalación de MariaDB con repicación
## 1.- Instalación

```sh
[root@elephant ~]# yum -y install MariaDB-server MariaDB-client
Complementos cargados:amazon-id, rhui-lb, search-disabled-repos
mariadb                                                                                                                                                                                                                | 2.9 kB  00:00:00     
rhui-REGION-client-config-server-7                                                                                                                                                                                     | 2.9 kB  00:00:00     
rhui-REGION-rhel-server-releases                                                                                                                                                                                       | 3.5 kB  00:00:00     
rhui-REGION-rhel-server-rh-common                                                                                                                                                                                      | 3.8 kB  00:00:00     
(1/8): mariadb/primary_db                                                                                                                                                                                              |  19 kB  00:00:00     
(2/8): rhui-REGION-client-config-server-7/x86_64/primary_db                                                                                                                                                            | 6.6 kB  00:00:00     
(3/8): rhui-REGION-rhel-server-releases/7Server/x86_64/updateinfo                                                                                                                                                      | 2.4 MB  00:00:00     
(4/8): rhui-REGION-rhel-server-releases/7Server/x86_64/group                                                                                                                                                           | 709 kB  00:00:00     
(5/8): rhui-REGION-rhel-server-rh-common/7Server/x86_64/group                                                                                                                                                          |  104 B  00:00:00     
(6/8): rhui-REGION-rhel-server-rh-common/7Server/x86_64/primary_db                                                                                                                                                     | 119 kB  00:00:00     
(7/8): rhui-REGION-rhel-server-rh-common/7Server/x86_64/updateinfo                                                                                                                                                     |  32 kB  00:00:00     
(8/8): rhui-REGION-rhel-server-releases/7Server/x86_64/primary_db                                                                                                                                                      |  44 MB  00:00:00     
Resolviendo dependencias
--> Ejecutando prueba de transacción
---> Paquete MariaDB-client.x86_64 0:10.1.29-1.el7.centos debe ser instalado
---> Paquete MariaDB-server.x86_64 0:10.1.29-1.el7.centos debe ser instalado
--> Resolución de dependencias finalizada

Dependencias resueltas

==============================================================================================================================================================================================================================================
 Package                                                     Arquitectura                                        Versión                                                           Repositorio                                          Tamaño
==============================================================================================================================================================================================================================================
Instalando:
 MariaDB-client                                              x86_64                                              10.1.29-1.el7.centos                                              mariadb                                               39 M
 MariaDB-server                                              x86_64                                              10.1.29-1.el7.centos                                              mariadb                                              104 M

Resumen de la transacción
==============================================================================================================================================================================================================================================
Instalar  2 Paquetes

Tamaño total de la descarga: 144 M
Tamaño instalado: 624 M
Downloading packages:
(1/2): MariaDB-10.1.29-centos7-x86_64-client.rpm                                                                                                                                                                       |  39 MB  00:00:01     
(2/2): MariaDB-10.1.29-centos7-x86_64-server.rpm                                                                                                                                                                       | 104 MB  00:00:03     
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Total                                                                                                                                                                                                          44 MB/s | 144 MB  00:00:03     
Running transaction check
Running transaction test
Transaction test succeeded
Running transaction
  Instalando    : MariaDB-client-10.1.29-1.el7.centos.x86_64                                                                                                                                                                              1/2 
  Instalando    : MariaDB-server-10.1.29-1.el7.centos.x86_64                                                                                                                                                                              2/2 
  Comprobando   : MariaDB-client-10.1.29-1.el7.centos.x86_64                                                                                                                                                                              1/2 
  Comprobando   : MariaDB-server-10.1.29-1.el7.centos.x86_64                                                                                                                                                                              2/2 

Instalado:
  MariaDB-client.x86_64 0:10.1.29-1.el7.centos                                                                          MariaDB-server.x86_64 0:10.1.29-1.el7.centos                                                                         

¡Listo!
```

## 2.-You should not need to build a /etc/my.cnf file to start your MySQL server

```sh
[mysqld]
log-bin
server_id=1
replicate-do-db=employees
bind-address=0.0.0.0
```

## 3.- Start the mysqld service.

```sh
[root@elephant ~]# systemctl start mariadb
[root@elephant ~]# systemctl enable mariadb
[root@elephant ~]# systemctl status mariadb
● mariadb.service - MariaDB database server
   Loaded: loaded (/usr/lib/systemd/system/mariadb.service; enabled; vendor preset: disabled)
  Drop-In: /etc/systemd/system/mariadb.service.d
           └─migrated-from-my.cnf-settings.conf
   Active: active (running) since lun 2017-11-27 14:15:15 CST; 14s ago
 Main PID: 12834 (mysqld)
   Status: "Taking your SQL requests now..."
   CGroup: /system.slice/mariadb.service
           └─12834 /usr/sbin/mysqld

nov 27 14:15:15 elephant.vinkos mysqld[12834]: 2017-11-27 20:15:15 139725037652224 [Note] InnoDB: Highest supported file format is Barracuda.
nov 27 14:15:15 elephant.vinkos mysqld[12834]: 2017-11-27 20:15:15 139725037652224 [Note] InnoDB: 128 rollback segment(s) are active.
nov 27 14:15:15 elephant.vinkos mysqld[12834]: 2017-11-27 20:15:15 139725037652224 [Note] InnoDB: Waiting for purge to start
nov 27 14:15:15 elephant.vinkos mysqld[12834]: 2017-11-27 20:15:15 139725037652224 [Note] InnoDB:  Percona XtraDB (http://www.percona.com) 5.6.36-82.2 started; log sequence number 292620240
nov 27 14:15:15 elephant.vinkos mysqld[12834]: 2017-11-27 20:15:15 139724253558528 [Note] InnoDB: Dumping buffer pool(s) not yet started
nov 27 14:15:15 elephant.vinkos mysqld[12834]: 2017-11-27 20:15:15 139725037652224 [Note] Plugin 'FEEDBACK' is disabled.
nov 27 14:15:15 elephant.vinkos mysqld[12834]: 2017-11-27 20:15:15 139725037652224 [Note] Server socket created on IP: '0.0.0.0'.
nov 27 14:15:15 elephant.vinkos mysqld[12834]: 2017-11-27 20:15:15 139725037652224 [Note] /usr/sbin/mysqld: ready for connections.
nov 27 14:15:15 elephant.vinkos mysqld[12834]: Version: '10.1.29-MariaDB'  socket: '/var/lib/mysql/mysql.sock'  port: 3306  MariaDB Server
nov 27 14:15:15 elephant.vinkos systemd[1]: Started MariaDB database server.
[root@elephant ~]# mysqladmin -u root -p version
Enter password: 
mysqladmin  Ver 9.1 Distrib 10.1.29-MariaDB, for Linux on x86_64
Copyright (c) 2000, 2017, Oracle, MariaDB Corporation Ab and others.

Server version		10.1.29-MariaDB
Protocol version	10
Connection		Localhost via UNIX socket
UNIX socket		/var/lib/mysql/mysql.sock
Uptime:			13 min 6 sec
```

## 4.-Use /usr/bin/mysql_secure_installation to:

```sh
[root@elephant ~]# sudo mysql_secure_installation

NOTE: RUNNING ALL PARTS OF THIS SCRIPT IS RECOMMENDED FOR ALL MariaDB
      SERVERS IN PRODUCTION USE!  PLEASE READ EACH STEP CAREFULLY!

In order to log into MariaDB to secure it, we'll need the current
password for the root user.  If you've just installed MariaDB, and
you haven't set the root password yet, the password will be blank,
so you should just press enter here.

Enter current password for root (enter for none): 
ERROR 1045 (28000): Access denied for user 'root'@'localhost' (using password: NO)
Enter current password for root (enter for none): 
OK, successfully used password, moving on...

Setting the root password ensures that nobody can log into the MariaDB
root user without the proper authorisation.

You already have a root password set, so you can safely answer 'n'.

Change the root password? [Y/n] Y
New password: 
Re-enter new password: 
Password updated successfully!
Reloading privilege tables..
 ... Success!


By default, a MariaDB installation has an anonymous user, allowing anyone
to log into MariaDB without having to have a user account created for
them.  This is intended only for testing, and to make the installation
go a bit smoother.  You should remove them before moving into a
production environment.

Remove anonymous users? [Y/n] y
 ... Success!

Normally, root should only be allowed to connect from 'localhost'.  This
ensures that someone cannot guess at the root password from the network.

Disallow root login remotely? [Y/n] n
 ... skipping.

By default, MariaDB comes with a database named 'test' that anyone can
access.  This is also intended only for testing, and should be removed
before moving into a production environment.

Remove test database and access to it? [Y/n] y
 - Dropping test database...
 ... Success!
 - Removing privileges on test database...
 ... Success!

Reloading the privilege tables will ensure that all changes made so far
will take effect immediately.

Reload privilege tables now? [Y/n] y
 ... Success!

Cleaning up...

All done!  If you've completed all of the above steps, your MariaDB
installation should now be secure.

Thanks for using MariaDB!
```

## 5.-On the master MySQL node, grant replication privileges for your replica node:

```sh
MariaDB [(none)]> GRANT REPLICATION SLAVE ON *.* TO 'root'@'horse' IDENTIFIED BY 'password';
Query OK, 0 rows affected (0.00 sec)
```

## 6.-In a second terminal session, log into the MySQL master and show its status:

```sh
MariaDB [(none)]> SHOW MASTER STATUS;
+---------------------+-----------+--------------+------------------+
| File                | Position  | Binlog_Do_DB | Binlog_Ignore_DB |
+---------------------+-----------+--------------+------------------+
| elephant-bin.000006 | 172308287 |              |                  |
+---------------------+-----------+--------------+------------------+
1 row in set (0.00 sec)
```

## 7.-Login to the replica server and configure a connection to the master:

```sh
MariaDB [(none)]> CHANGE MASTER TO
    -> MASTER_HOST='elephant',
    -> MASTER_USER='root',
    -> MASTER_PASSWORD='password',
    -> MASTER_PORT=3306,
    -> MASTER_LOG_FILE='elephant-bin.000006',
    -> MASTER_LOG_POS=172308287,
    -> MASTER_CONNECT_RETRY=10,
    -> MASTER_USE_GTID=current_pos;
Query OK, 0 rows affected (0.00 sec)
```

## 8.-Initiate slave operations on the replica

```sh
MariaDB [(none)]> START SLAVE;
Query OK, 0 rows affected (0.01 sec)
MariaDB [(none)]> SHOW SLAVE STATUS\G;
*************************** 1. row ***************************
               Slave_IO_State: Waiting for master to send event
                  Master_Host: elephant
                  Master_User: root
                  Master_Port: 3306
                Connect_Retry: 10
              Master_Log_File: elephant-bin.000007
          Read_Master_Log_Pos: 637
               Relay_Log_File: horse-relay-bin.000002
                Relay_Log_Pos: 660
        Relay_Master_Log_File: elephant-bin.000007
             Slave_IO_Running: Yes
            Slave_SQL_Running: Yes
              Replicate_Do_DB: 
          Replicate_Ignore_DB: 
           Replicate_Do_Table: 
       Replicate_Ignore_Table: 
      Replicate_Wild_Do_Table: 
  Replicate_Wild_Ignore_Table: 
                   Last_Errno: 0
                   Last_Error: 
                 Skip_Counter: 0
          Exec_Master_Log_Pos: 637
              Relay_Log_Space: 958
              Until_Condition: None
               Until_Log_File: 
                Until_Log_Pos: 0
           Master_SSL_Allowed: No
           Master_SSL_CA_File: 
           Master_SSL_CA_Path: 
              Master_SSL_Cert: 
            Master_SSL_Cipher: 
               Master_SSL_Key: 
        Seconds_Behind_Master: 0
Master_SSL_Verify_Server_Cert: No
                Last_IO_Errno: 0
                Last_IO_Error: 
               Last_SQL_Errno: 0
               Last_SQL_Error: 
  Replicate_Ignore_Server_Ids: 
             Master_Server_Id: 1
               Master_SSL_Crl: 
           Master_SSL_Crlpath: 
                   Using_Gtid: Current_Pos
                  Gtid_IO_Pos: 0-1-191
      Replicate_Do_Domain_Ids: 
  Replicate_Ignore_Domain_Ids: 
                Parallel_Mode: conservative
1 row in set (0.01 sec)
```


