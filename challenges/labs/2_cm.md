```sh
[root@ip-172-31-17-0 ~]# ls /etc/yum.repos.d
cloudera-manager.repo  redhat.repo                     redhat-rhui.repo
MariaDB10.repo         redhat-rhui-client-config.repo  rhui-load-balancers.conf
```


## Comando

```sh
[root@ip-172-31-17-0 ~]# /usr/share/cmf/schema/scm_prepare_database.sh mysql -h ip-172-31-20-143.ec2.internal -P 3306 -utemp -ptemp --scm-host ip-172-31-17-0.ec2.internal scm scm scm_password
```

## Respuesta
```sh
JAVA_HOME=/usr/java/jdk1.7.0_67-cloudera
Verifying that we can write to /etc/cloudera-scm-server
Creating SCM configuration file in /etc/cloudera-scm-server
Executing:  /usr/java/jdk1.7.0_67-cloudera/bin/java -cp /usr/share/java/mysql-connector-java.jar:/usr/share/java/oracle-connector-java.jar:/usr/share/cmf/schema/../lib/* com.cloudera.enterprise.dbutil.DbCommandExecutor /etc/cloudera-scm-server/db.properties com.cloudera.cmf.db.
[                          main] DbCommandExecutor              INFO  Successfully connected to database.
All done, your SCM database is configured correctly!
```


