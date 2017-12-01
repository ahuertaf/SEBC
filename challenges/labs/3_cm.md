
## The command and output for hdfs dfs -ls /user

```sh
[hdfs@ip-172-31-17-0 ec2-user]$ hdfs dfs -ls /user
Found 11 items
drwxr-xr-x   - admin    admin               0 2017-12-01 11:47 /user/admin
drwxr-xr-x   - hdfs     supergroup          0 2017-12-01 11:52 /user/haley
drwxr-xr-x   - hdfs     supergroup          0 2017-12-01 11:46 /user/hdfs
drwxrwxrwx   - mapred   hadoop              0 2017-12-01 11:36 /user/history
drwxrwxr-t   - hive     hive                0 2017-12-01 11:37 /user/hive
drwxrwxr-x   - hue      hue                 0 2017-12-01 11:38 /user/hue
drwxrwxr-x   - oozie    oozie               0 2017-12-01 11:38 /user/oozie
drwxr-xr-x   - hdfs     supergroup          0 2017-12-01 11:51 /user/saturn
drwxr-x--x   - spark    spark               0 2017-12-01 11:37 /user/spark
```
## The command and output from the CM API call ../api/v14/hosts

```sh
[ec2-user@ip-172-31-17-0 ~]$ curl -u admin:admin 'http://localhost:7180/api/v14/hosts'
{
  "items" : [ {
    "hostId" : "318e31e3-9d6a-4d55-86d4-e533c5588d79",
    "ipAddress" : "172.31.17.0",
    "hostname" : "ip-172-31-17-0.ec2.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-17-0.ec2.internal:7180/cmf/hostRedirect/318e31e3-9d6a-4d55-86d4-e533c5588d79",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 8,
    "numPhysicalCores" : 4,
    "totalPhysMemBytes" : 33567498240
  }, {
    "hostId" : "bef871fa-aaa3-4fab-88c0-76fe2195d85f",
    "ipAddress" : "172.31.20.143",
    "hostname" : "ip-172-31-20-143.ec2.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-17-0.ec2.internal:7180/cmf/hostRedirect/bef871fa-aaa3-4fab-88c0-76fe2195d85f",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 8,
    "numPhysicalCores" : 4,
    "totalPhysMemBytes" : 33567498240
  }, {
    "hostId" : "527ba12c-26b7-4f9c-a20f-9177e2421c82",
    "ipAddress" : "172.31.23.34",
    "hostname" : "ip-172-31-23-34.ec2.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-17-0.ec2.internal:7180/cmf/hostRedirect/527ba12c-26b7-4f9c-a20f-9177e2421c82",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 8,
    "numPhysicalCores" : 4,
    "totalPhysMemBytes" : 33567498240
  }, {
    "hostId" : "a38a215b-8c13-435f-8344-d0a5c3a25cb4",
    "ipAddress" : "172.31.23.44",
    "hostname" : "ip-172-31-23-44.ec2.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-17-0.ec2.internal:7180/cmf/hostRedirect/a38a215b-8c13-435f-8344-d0a5c3a25cb4",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 8,
    "numPhysicalCores" : 4,
    "totalPhysMemBytes" : 33567498240
  }, {
    "hostId" : "e01193c0-f3e3-4011-b768-5a94a859800e",
    "ipAddress" : "172.31.24.48",
    "hostname" : "ip-172-31-24-48.ec2.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-17-0.ec2.internal:7180/cmf/hostRedirect/e01193c0-f3e3-4011-b768-5a94a859800e",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 8,
    "numPhysicalCores" : 4,
    "totalPhysMemBytes" : 33567498240
  } ]
```
## The command and output from the CM API call ../api/v8/clusters/<githubName>/services

```sh
[ec2-user@ip-172-31-17-0 ~]$ curl -u admin:admin 'http://localhost:7180/api/v8/clusters/ahuertaf/services'
{
  "items" : [ {
    "name" : "hive",
    "type" : "HIVE",
    "clusterRef" : {
      "clusterName" : "cluster"
    },
    "serviceUrl" : "http://ip-172-31-17-0.ec2.internal:7180/cmf/serviceRedirect/hive",
    "serviceState" : "STARTED",
    "healthSummary" : "GOOD",
    "healthChecks" : [ {
      "name" : "HIVE_HIVEMETASTORES_HEALTHY",
      "summary" : "GOOD"
    }, {
      "name" : "HIVE_HIVESERVER2S_HEALTHY",
      "summary" : "GOOD"
    } ],
    "configStalenessStatus" : "FRESH",
    "clientConfigStalenessStatus" : "FRESH",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "displayName" : "Hive"
  }, {
    "name" : "zookeeper",
    "type" : "ZOOKEEPER",
    "clusterRef" : {
      "clusterName" : "cluster"
    },
    "serviceUrl" : "http://ip-172-31-17-0.ec2.internal:7180/cmf/serviceRedirect/zookeeper",
    "serviceState" : "STARTED",
    "healthSummary" : "GOOD",
    "healthChecks" : [ {
      "name" : "ZOOKEEPER_CANARY_HEALTH",
      "summary" : "GOOD"
    }, {
      "name" : "ZOOKEEPER_SERVERS_HEALTHY",
      "summary" : "GOOD"
    } ],
    "configStalenessStatus" : "FRESH",
    "clientConfigStalenessStatus" : "FRESH",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "displayName" : "ZooKeeper"
  }, {
    "name" : "hue",
    "type" : "HUE",
    "clusterRef" : {
      "clusterName" : "cluster"
    },
    "serviceUrl" : "http://ip-172-31-17-0.ec2.internal:7180/cmf/serviceRedirect/hue",
    "serviceState" : "STARTED",
    "healthSummary" : "GOOD",
    "healthChecks" : [ {
      "name" : "HUE_HUE_SERVERS_HEALTHY",
      "summary" : "GOOD"
    }, {
      "name" : "HUE_LOAD_BALANCER_HEALTHY",
      "summary" : "GOOD"
    } ],
    "configStalenessStatus" : "FRESH",
    "clientConfigStalenessStatus" : "FRESH",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "displayName" : "Hue"
  }, {
    "name" : "oozie",
    "type" : "OOZIE",
    "clusterRef" : {
      "clusterName" : "cluster"
    },
    "serviceUrl" : "http://ip-172-31-17-0.ec2.internal:7180/cmf/serviceRedirect/oozie",
    "serviceState" : "STARTED",
    "healthSummary" : "GOOD",
    "healthChecks" : [ {
      "name" : "OOZIE_OOZIE_SERVERS_HEALTHY",
      "summary" : "GOOD"
    } ],
    "configStalenessStatus" : "FRESH",
    "clientConfigStalenessStatus" : "FRESH",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "displayName" : "Oozie"
  }, {
    "name" : "yarn",
    "type" : "YARN",
    "clusterRef" : {
      "clusterName" : "cluster"
    },
    "serviceUrl" : "http://ip-172-31-17-0.ec2.internal:7180/cmf/serviceRedirect/yarn",
    "serviceState" : "STARTED",
    "healthSummary" : "GOOD",
    "healthChecks" : [ {
      "name" : "YARN_JOBHISTORY_HEALTH",
      "summary" : "GOOD"
    }, {
      "name" : "YARN_NODE_MANAGERS_HEALTHY",
      "summary" : "GOOD"
    }, {
      "name" : "YARN_RESOURCEMANAGERS_HEALTH",
      "summary" : "GOOD"
    }, {
      "name" : "YARN_USAGE_AGGREGATION_HEALTH",
      "summary" : "DISABLED"
    } ],
    "configStalenessStatus" : "FRESH",
    "clientConfigStalenessStatus" : "FRESH",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "displayName" : "YARN (MR2 Included)"
  }, {
    "name" : "spark_on_yarn",
    "type" : "SPARK_ON_YARN",
    "clusterRef" : {
      "clusterName" : "cluster"
    },
    "serviceUrl" : "http://ip-172-31-17-0.ec2.internal:7180/cmf/serviceRedirect/spark_on_yarn",
    "serviceState" : "STARTED",
    "healthSummary" : "GOOD",
    "healthChecks" : [ ],
    "configStalenessStatus" : "FRESH",
    "clientConfigStalenessStatus" : "FRESH",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "displayName" : "Spark"
  }, {
    "name" : "hdfs",
    "type" : "HDFS",
    "clusterRef" : {
      "clusterName" : "cluster"
    },
    "serviceUrl" : "http://ip-172-31-17-0.ec2.internal:7180/cmf/serviceRedirect/hdfs",
    "serviceState" : "STARTED",
    "healthSummary" : "GOOD",
    "healthChecks" : [ {
      "name" : "HDFS_BLOCKS_WITH_CORRUPT_REPLICAS",
      "summary" : "GOOD"
    }, {
      "name" : "HDFS_CANARY_HEALTH",
      "summary" : "GOOD"
    }, {
      "name" : "HDFS_DATA_NODES_HEALTHY",
      "summary" : "GOOD"
    }, {
      "name" : "HDFS_FREE_SPACE_REMAINING",
      "summary" : "GOOD"
    }, {
      "name" : "HDFS_HA_NAMENODE_HEALTH",
      "summary" : "GOOD"
    }, {
      "name" : "HDFS_MISSING_BLOCKS",
      "summary" : "GOOD"
    }, {
      "name" : "HDFS_UNDER_REPLICATED_BLOCKS",
      "summary" : "GOOD"
    } ],
    "configStalenessStatus" : "FRESH",
    "clientConfigStalenessStatus" : "FRESH",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "displayName" : "HDFS"
  } ]
}
```
