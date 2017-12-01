# Record the following in challenges/labs/1_db-server.md

## A command and output that shows the hostname of your database server

```sh
MariaDB [(none)]> select @@hostname;
+-------------------------------+
| @@hostname                    |
+-------------------------------+
| ip-172-31-20-143.ec2.internal |
+-------------------------------+
1 row in set (0.00 sec)
```

## A command and output that reports the database server version

```sh
MariaDB [(none)]> select version();
+-----------------+
| version()       |
+-----------------+
| 10.1.29-MariaDB |
+-----------------+
1 row in set (0.00 sec)
```

## A command and output that lists all the databases in the server

```sh
MariaDB [(none)]> SHOW DATABASES;
+--------------------+
| Database           |
+--------------------+
| amon               |
| hive               |
| hue                |
| information_schema |
| metastore          |
| mysql              |
| nav                |
| navms              |
| oozie              |
| performance_schema |
| rman               |
| sentry             |
+--------------------+
12 rows in set (0.00 sec)
```

