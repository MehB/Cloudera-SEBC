###### Stop and Start Hive with API:


```
[hadoop01@ip-172-31-14-88 ~]$ curl -X POST -u hadoop01:cloudera "http://52.35.67.233:7180/api/v1/clusters/MehB-Cluster/services/hive/commands/stop"
{
  "id" : 375,
  "name" : "Stop",
  "startTime" : "2017-03-08T11:54:55.206Z",
  "active" : true,
  "serviceRef" : {
    "clusterName" : "cluster",
    "serviceName" : "hive"
  }
}
```


```
[hadoop01@ip-172-31-14-88 ~]$ curl -X POST -u hadoop01:cloudera "http://52.35.67.233:7180/api/v1/clusters/MehB-Cluster/services/hive/commands/restart"
{
  "id" : 379,
  "name" : "Restart",
  "startTime" : "2017-03-08T11:55:30.642Z",
  "active" : true,
  "serviceRef" : {
    "clusterName" : "cluster",
    "serviceName" : "hive"
  }
  ```
