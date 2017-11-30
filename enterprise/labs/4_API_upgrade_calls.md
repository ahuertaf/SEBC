# Upgrade Cloudera Manager

## Upgrade to the latest C5.9 release
Use the documentation here

Use the API on the command line to:

## Report the latest available version of the API

```sh
[hduser@elephant ~]$ curl -X GET -u ahuertaf:password 'http://localhost:7180/api/version'
v18
```

## Report the CM version

```sh
[hduser@elephant ~]$ curl -u ahuertaf:password 'http://localhost:7180/api/v18/cm/version'
{
  "version" : "5.13.0",
  "buildUser" : "jenkins",
  "buildTimestamp" : "20171002-1719",
  "gitHash" : "bd657e597e6743c458ee2c9aabe808b7c972981c",
  "snapshot" : false
```

## List all CM users

```sh
[hduser@elephant ~]$ curl -u ahuertaf:password 'http://localhost:7180/api/v18/users'
{
  "items" : [ {
    "name" : "admin",
    "roles" : [ "ROLE_LIMITED" ]
  }, {
    "name" : "ahuertaf",
    "roles" : [ "ROLE_ADMIN" ]
  }, {
    "name" : "minotaur",
    "roles" : [ "ROLE_CONFIGURATOR" ]
  } ]
```

## Report the database server in use by CM

```sh
[hduser@elephant ~]$ curl -u ahuertaf:password 'http://localhost:7180/api/v18/cm/scmDbInfo'
{
  "scmDbType" : "MYSQL",
  "embeddedDbUsed" : false
}
```
