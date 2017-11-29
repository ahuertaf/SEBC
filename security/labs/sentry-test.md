# Verify user privileges

Authenticate your user as a Kerberos principal
Use beeline to confirm your principal sees no tables
!connect jdbc:hive2://localhost:10000/default;principal=hive/fdqn@REALM.COM
Replace fqdn with your host's fully-qualified domain name
Use your Linux account/password to authenticate when prompted
Enter SHOW TABLES;
The statement should return an empty set because no authorizations are in place
Copy the transcript of this section to security/labs/sentry-test.md

```sh
kinit ahuertaf
Password for ahuertaf@VINKOS.COM: 
[hduser@lion ~]$ beeline
Beeline version 1.1.0-cdh5.12.1 by Apache Hive
beeline> !connect jdbc:hive2://localhost:10000/default;principal=hive/lion@VINKOS.COM
scan complete in 2ms
Connecting to jdbc:hive2://localhost:10000/default;principal=hive/lion@VINKOS.COM
Connected to: Apache Hive (version 1.1.0-cdh5.12.1)
Driver: Hive JDBC (version 1.1.0-cdh5.12.1)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://lion:10000/default> SHOW TABLES;
INFO  : Compiling command(queryId=hive_20171129195959_ea839c59-2388-48a3-8b78-d7d045ba0b0a): SHOW TABLES
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20171129195959_ea839c59-2388-48a3-8b78-d7d045ba0b0a); Time taken: 0.057 seconds
INFO  : Executing command(queryId=hive_20171129195959_ea839c59-2388-48a3-8b78-d7d045ba0b0a): SHOW TABLES
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171129195959_ea839c59-2388-48a3-8b78-d7d045ba0b0a); Time taken: 0.121 seconds
INFO  : OK
+-----------+--+
| tab_name  |
+-----------+--+
| sample_0  |
| sample_1  |
| sample_2  |
| sample_3  |
| sample_4  |
| sample_5  |
+-----------+--+
6 rows selected (0.298 seconds)

```

# Create a Sentry role with full authorization

In beeline:
CREATE ROLE sentry_admin;
GRANT ALL ON SERVER server1 TO ROLE sentry_admin;
GRANT ROLE sentry_admin TO GROUP {your_primary};
SHOW TABLES;
The statement should now return all tables

```sh
0: jdbc:hive2://localhost:10000/default> CREATE ROLE sentry_admin;
INFO  : Compiling command(queryId=hive_20171129194848_72aaeb6e-c984-4dbe-9a57-fea3de761ca0): CREATE ROLE sentry_admin
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20171129194848_72aaeb6e-c984-4dbe-9a57-fea3de761ca0); Time taken: 0.061 seconds
INFO  : Executing command(queryId=hive_20171129194848_72aaeb6e-c984-4dbe-9a57-fea3de761ca0): CREATE ROLE sentry_admin
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171129194848_72aaeb6e-c984-4dbe-9a57-fea3de761ca0); Time taken: 0.424 seconds
INFO  : OK
No rows affected (0.499 seconds)
0: jdbc:hive2://localhost:10000/default> GRANT ALL ON SERVER server1 TO ROLE sentry_admin;
INFO  : Compiling command(queryId=hive_20171129194949_7806812b-41e6-4472-92a0-cbea065b88cf): GRANT ALL ON SERVER server1 TO ROLE sentry_admin
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20171129194949_7806812b-41e6-4472-92a0-cbea065b88cf); Time taken: 0.064 seconds
INFO  : Executing command(queryId=hive_20171129194949_7806812b-41e6-4472-92a0-cbea065b88cf): GRANT ALL ON SERVER server1 TO ROLE sentry_admin
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171129194949_7806812b-41e6-4472-92a0-cbea065b88cf); Time taken: 0.078 seconds
INFO  : OK
No rows affected (0.154 seconds)
0: jdbc:hive2://localhost:10000/default> GRANT ROLE sentry_admin TO GROUP ahuertaf;
INFO  : Compiling command(queryId=hive_20171129195151_d5d03236-08a7-4836-b38f-c1c4a5037640): GRANT ROLE sentry_admin TO GROUP ahuertaf
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20171129195151_d5d03236-08a7-4836-b38f-c1c4a5037640); Time taken: 0.057 seconds
INFO  : Executing command(queryId=hive_20171129195151_d5d03236-08a7-4836-b38f-c1c4a5037640): GRANT ROLE sentry_admin TO GROUP ahuertaf
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171129195151_d5d03236-08a7-4836-b38f-c1c4a5037640); Time taken: 0.025 seconds
INFO  : OK
No rows affected (0.098 seconds)
0: jdbc:hive2://localhost:10000/default> SHOW TABLES;
INFO  : Compiling command(queryId=hive_20171129195959_ea839c59-2388-48a3-8b78-d7d045ba0b0a): SHOW TABLES
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20171129195959_ea839c59-2388-48a3-8b78-d7d045ba0b0a); Time taken: 0.057 seconds
INFO  : Executing command(queryId=hive_20171129195959_ea839c59-2388-48a3-8b78-d7d045ba0b0a): SHOW TABLES
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171129195959_ea839c59-2388-48a3-8b78-d7d045ba0b0a); Time taken: 0.121 seconds
INFO  : OK
+-----------+--+
| tab_name  |
+-----------+--+
| sample_0  |
| sample_1  |
| sample_2  |
| sample_3  |
| sample_4  |
| sample_5  |
+-----------+--+
6 rows selected (0.298 seconds)
```

# Create additional test users

Add new users to all cluster nodes
$ sudo groupadd selector
$ sudo groupadd inserters
$ sudo useradd -u 1100 -g selector george
$ sudo useradd -u 1200 -g inserters ferdinand
$ kadmin.local: add_principal george
$ kadmin.local: add_principal ferdinand

```sh
[hduser@elephant ~]$ sudo groupadd selector
[hduser@elephant ~]$ sudo groupadd inserters
[hduser@elephant ~]$ sudo useradd -u 1100 -g selector george
[hduser@elephant ~]$ sudo useradd -u 1200 -g inserters ferdinand
[root@elephant ~]$kadmin.local
Authenticating as principal ahuertaf/admin@VINKOS.COM with password.
kadmin.local:  add_principal george
WARNING: no policy specified for george@VINKOS.COM; defaulting to no policy
Enter password for principal "george@VINKOS.COM": 
Re-enter password for principal "george@VINKOS.COM": 
Principal "george@VINKOS.COM" created.
kadmin.local:  add_principal ferdinand
WARNING: no policy specified for ferdinand@VINKOS.COM; defaulting to no policy
Enter password for principal "ferdinand@VINKOS.COM": 
Re-enter password for principal "ferdinand@VINKOS.COM": 
Principal "ferdinand@VINKOS.COM" created.
```

# Create test roles

Login to beeline as your admin user
CREATE ROLE reads;
CREATE ROLE writes;

```sh
0: jdbc:hive2://lion:10000/default> CREATE ROLE reads;
INFO  : Compiling command(queryId=hive_20171129201010_ea4d4db6-d08e-4006-9a28-4391ea6f9018): CREATE ROLE reads
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20171129201010_ea4d4db6-d08e-4006-9a28-4391ea6f9018); Time taken: 0.062 seconds
INFO  : Executing command(queryId=hive_20171129201010_ea4d4db6-d08e-4006-9a28-4391ea6f9018): CREATE ROLE reads
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171129201010_ea4d4db6-d08e-4006-9a28-4391ea6f9018); Time taken: 0.034 seconds
INFO  : OK
No rows affected (0.145 seconds)
0: jdbc:hive2://lion:10000/default> CREATE ROLE writes;
INFO  : Compiling command(queryId=hive_20171129201010_a1c1fd2c-99c9-4a95-9680-347e15b67f9e): CREATE ROLE writes
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20171129201010_a1c1fd2c-99c9-4a95-9680-347e15b67f9e); Time taken: 0.054 seconds
INFO  : Executing command(queryId=hive_20171129201010_a1c1fd2c-99c9-4a95-9680-347e15b67f9e): CREATE ROLE writes
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171129201010_a1c1fd2c-99c9-4a95-9680-347e15b67f9e); Time taken: 0.02 seconds
INFO  : OK
No rows affected (0.085 seconds)
```

# Grant read privilege for all tables to reads

GRANT SELECT ON DATABASE default TO ROLE reads;
GRANT ROLE reads TO GROUP selector;

```sh
0: jdbc:hive2://lion:10000/default> GRANT SELECT ON DATABASE default TO ROLE reads;
INFO  : Compiling command(queryId=hive_20171129201010_424b85e5-2468-406d-a70e-f7495a01a2f6): GRANT SELECT ON DATABASE default TO ROLE reads
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20171129201010_424b85e5-2468-406d-a70e-f7495a01a2f6); Time taken: 0.061 seconds
INFO  : Executing command(queryId=hive_20171129201010_424b85e5-2468-406d-a70e-f7495a01a2f6): GRANT SELECT ON DATABASE default TO ROLE reads
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171129201010_424b85e5-2468-406d-a70e-f7495a01a2f6); Time taken: 0.026 seconds
INFO  : OK
No rows affected (0.097 seconds)
0: jdbc:hive2://lion:10000/default> GRANT ROLE reads TO GROUP selector;
INFO  : Compiling command(queryId=hive_20171129201111_d3998bbb-6542-405b-9595-3b8a50dd30ae): GRANT ROLE reads TO GROUP selector
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20171129201111_d3998bbb-6542-405b-9595-3b8a50dd30ae); Time taken: 0.055 seconds
INFO  : Executing command(queryId=hive_20171129201111_d3998bbb-6542-405b-9595-3b8a50dd30ae): GRANT ROLE reads TO GROUP selector
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171129201111_d3998bbb-6542-405b-9595-3b8a50dd30ae); Time taken: 0.022 seconds
INFO  : OK
No rows affected (0.099 seconds)
```

# Grant read privilege for default.sample07 only to 'writes':

REVOKE ALL ON DATABASE default FROM ROLE writes;
GRANT SELECT ON default.sample_07 TO ROLE writes;
GRANT ROLE writes TO GROUP inserters;

```sh
INFO  : Compiling command(queryId=hive_20171129201414_57146001-6324-4689-b43e-084571eb5f13): REVOKE ALL ON DATABASE default FROM ROLE writes
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20171129201414_57146001-6324-4689-b43e-084571eb5f13); Time taken: 0.056 seconds
INFO  : Executing command(queryId=hive_20171129201414_57146001-6324-4689-b43e-084571eb5f13): REVOKE ALL ON DATABASE default FROM ROLE writes
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171129201414_57146001-6324-4689-b43e-084571eb5f13); Time taken: 0.059 seconds
INFO  : OK
No rows affected (0.125 seconds)
0: jdbc:hive2://lion:10000/default> GRANT SELECT ON default.sample_07 TO ROLE writes;
INFO  : Compiling command(queryId=hive_20171129201515_ebd62f2d-8298-46a9-af3b-1e755678e155): GRANT SELECT ON default.sample_07 TO ROLE writes
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20171129201515_ebd62f2d-8298-46a9-af3b-1e755678e155); Time taken: 0.054 seconds
INFO  : Executing command(queryId=hive_20171129201515_ebd62f2d-8298-46a9-af3b-1e755678e155): GRANT SELECT ON default.sample_07 TO ROLE writes
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171129201515_ebd62f2d-8298-46a9-af3b-1e755678e155); Time taken: 0.03 seconds
INFO  : OK
No rows affected (0.094 seconds)
0: jdbc:hive2://lion:10000/default> GRANT ROLE writes TO GROUP inserters;
INFO  : Compiling command(queryId=hive_20171129201515_308ac724-9d29-473a-b393-8e8ca9eccfc4): GRANT ROLE writes TO GROUP inserters
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20171129201515_308ac724-9d29-473a-b393-8e8ca9eccfc4); Time taken: 0.06 seconds
INFO  : Executing command(queryId=hive_20171129201515_308ac724-9d29-473a-b393-8e8ca9eccfc4): GRANT ROLE writes TO GROUP inserters
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171129201515_308ac724-9d29-473a-b393-8e8ca9eccfc4); Time taken: 0.029 seconds
INFO  : OK
No rows affected (0.099 seconds)
```
# kinit as george, then login to beeline

kinit as george, login to beeline, and use SHOW TABLES;
george should be able to see all tables
Repeat the process as ferdinand
ferdinand should see sample_07
Add the transcripts of these sessions to security/labs/sentry-test.md

```sh
[hduser@monkey ~]$ kinit george
Password for george@VINKOS.COM: 
[hduser@monkey ~]$ beeline
Beeline version 1.1.0-cdh5.12.1 by Apache Hive
beeline> !connect jdbc:hive2://lion:10000/default;principal=hive/lion@VINKOS.COM
scan complete in 2ms
Connecting to jdbc:hive2://lion:10000/default;principal=hive/lion@VINKOS.COM
Connected to: Apache Hive (version 1.1.0-cdh5.12.1)
Driver: Hive JDBC (version 1.1.0-cdh5.12.1)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://lion:10000/default> SHOW TABLES;
INFO  : Compiling command(queryId=hive_20171129201818_6719e59e-22e4-40e5-b809-3325d18cacef): SHOW TABLES
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20171129201818_6719e59e-22e4-40e5-b809-3325d18cacef); Time taken: 0.084 seconds
INFO  : Executing command(queryId=hive_20171129201818_6719e59e-22e4-40e5-b809-3325d18cacef): SHOW TABLES
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171129201818_6719e59e-22e4-40e5-b809-3325d18cacef); Time taken: 0.12 seconds
INFO  : OK
+-----------+--+
| tab_name  |
+-----------+--+
| sample_0  |
| sample_1  |
| sample_2  |
| sample_3  |
| sample_4  |
| sample_5  |
| sample_07  |
+-----------+--+
7 rows selected (0.291 seconds)
[hduser@monkey ~]$ kinit ferdinand
Password for ferdinand@VINKOS.COM: 
[hduser@monkey ~]$ beeline
Beeline version 1.1.0-cdh5.12.1 by Apache Hive
beeline> !connect jdbc:hive2://lion:10000/default;principal=hive/lion@VINKOS.COM
scan complete in 1ms
Connecting to jdbc:hive2://lion:10000/default;principal=hive/lion@VINKOS.COM
Connected to: Apache Hive (version 1.1.0-cdh5.12.1)
Driver: Hive JDBC (version 1.1.0-cdh5.12.1)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://lion:10000/default> SHOW TABLES;
INFO  : Compiling command(queryId=hive_20171129202020_67d13154-97e8-4b33-8610-6e7f31357ab3): SHOW TABLES
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20171129202020_67d13154-97e8-4b33-8610-6e7f31357ab3); Time taken: 0.055 seconds
INFO  : Executing command(queryId=hive_20171129202020_67d13154-97e8-4b33-8610-6e7f31357ab3): SHOW TABLES
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171129202020_67d13154-97e8-4b33-8610-6e7f31357ab3); Time taken: 0.124 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| sample_07  |
+------------+--+
1 row selected (0.197 seconds)
```

