# Use the API
## Status inicial
```sh
[hduser@elephant ~]$ curl -u ahuertaf:password 'http://localhost:7180/api/v2/clusters/ahuertaf/services/hive'
{
  "name" : "hive",
  "type" : "HIVE",
  "clusterRef" : {
    "clusterName" : "cluster"
  },
  "serviceUrl" : "http://elephant:7180/cmf/serviceRedirect/hive",
  "serviceState" : "STARTED",
  "healthSummary" : "GOOD",
  "healthChecks" : [ {
    "name" : "HIVE_HIVEMETASTORES_HEALTHY",
    "summary" : "GOOD"
  }, {
    "name" : "HIVE_HIVESERVER2S_HEALTHY",
    "summary" : "GOOD"
  } ],
  "configStale" : false,
  "maintenanceMode" : false,
  "maintenanceOwners" : [ ],
  "displayName" : "Hive"
}
```
## Detener Hive

```sh
[hduser@elephant ~]$ curl -X POST -u ahuertaf:password 'http://localhost:7180/api/v2/clusters/ahuertaf/services/hive/commands/stop'
{
  "id" : 1083,
  "name" : "Stop",
  "startTime" : "2017-11-30T17:22:48.893Z",
  "active" : true,
  "serviceRef" : {
    "clusterName" : "cluster",
    "serviceName" : "hive"
  }
}[hduser@elephant ~]$ url -u ahuertaf:password 'http://localhost:7180/api/v2/clusters/ahuertaf/services/hive'
{
  "name" : "hive",
  "type" : "HIVE",
  "clusterRef" : {
    "clusterName" : "cluster"
  },
  "serviceUrl" : "http://elephant:7180/cmf/serviceRedirect/hive",
  "serviceState" : "STOPPED",
  "healthSummary" : "DISABLED",
  "healthChecks" : [ {
    "name" : "HIVE_HIVEMETASTORES_HEALTHY",
    "summary" : "DISABLED"
  }, {
    "name" : "HIVE_HIVESERVER2S_HEALTHY",
    "summary" : "DISABLED"
  } ],
  "configStale" : false,
  "maintenanceMode" : false,
  "maintenanceOwners" : [ ],
  "displayName" : "Hive"
}
```
## Iniciar de nuevo Hive

```sh
[hduser@elephant ~]$ curl -X POST -u ahuertaf:password 'http://localhost:7180/api/v2/clustersahuertaf/services/hive/commands/start'
{
  "id" : 1089,
  "name" : "Start",
  "startTime" : "2017-11-30T17:23:21.056Z",
  "active" : true,
  "serviceRef" : {
    "clusterName" : "cluster",
    "serviceName" : "hive"
  }
}[hduser@elephant ~]$ curl u ahuertaf:password 'http://localhost:7180/api/v2/clusters/ahuertaf/services/hive'
{
  "name" : "hive",
  "type" : "HIVE",
  "clusterRef" : {
    "clusterName" : "cluster"
  },
  "serviceUrl" : "http://elephant:7180/cmf/serviceRedirect/hive",
  "serviceState" : "STARTING",
  "healthSummary" : "DISABLED",
  "healthChecks" : [ {
    "name" : "HIVE_HIVEMETASTORES_HEALTHY",
    "summary" : "DISABLED"
  }, {
    "name" : "HIVE_HIVESERVER2S_HEALTHY",
    "summary" : "DISABLED"
  } ],
  "configStale" : false,
  "maintenanceMode" : false,
  "maintenanceOwners" : [ ],
  "displayName" : "Hive"
}
```
