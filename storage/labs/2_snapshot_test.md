List the commands and output for each step below in storage/labs/2_snapshot_test.md.

# Create a precious directory in HDFS; copy the ZIP course file into it.

```sh
[hdfs@elephant ~]$ hdfs dfs -mkdir /user/admin/ahuertaf/precious
[hdfs@elephant ~]$ hdfs dfs -put SEBC-master.zip /user/admin/ahuertaf/precious/
[hdfs@elephant ~]$ hdfs dfs -ls /user/admin/ahuertaf/precious/
Found 1 items
-rw-r--r--   3 hdfs admin     474833 2017-11-28 11:52 /user/admin/ahuertaf/precious/SEBC-master.zip
```

# Enable snapshots for precious
```sh
[hdfs@elephant ~]$ hdfs dfs -allowSnapshot /user/admin/ahuertaf/precious
```

# Create a snapshot called sebc-hdfs-test
```sh
[hdfs@elephant ~]$ hdfs dfs -createSnapshot /user/admin/ahuertaf/precious sebc-hdfs-test
```

# Delete the directory
```sh
[hdfs@elephant ~]$ hdfs dfs -rm -R /user/admin/ahuertaf/precious/
rm: Failed to move to trash: hdfs://horse:8020/user/admin/ahuertaf/precious: The directory /user/admin/ahuertaf/precious cannot be deleted since /user/admin/ahuertaf/precious is snapshottable and already has snapshots
```

# Delete the ZIP file

```sh
[hdfs@elephant ~]$ hdfs dfs -rm /user/admin/ahuertaf/precious/SEBC-master.zip
17/11/28 12:01:21 INFO fs.TrashPolicyDefault: Moved: 'hdfs://horse:8020/user/admin/ahuertaf/precious/SEBC-master.zip' to trash at: hdfs://horse:8020/user/hdfs/.Trash/Current/user/admin/ahuertaf/precious/SEBC-master.zip
```


Capture the NameNode web UI screen that lists snapshots in storage/labs/2_snapshot_list.png


