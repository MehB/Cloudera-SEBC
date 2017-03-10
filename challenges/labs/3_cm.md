## Create HDFS users
```
[hdfs@ip-172-31-5-225 ~]$ hdfs dfs -mkdir /user/neymar
[hdfs@ip-172-31-5-225 ~]$ hdfs dfs -mkdir /user/ronaldo
```

## Change permissions 

```
[hdfs@ip-172-31-5-225 ~]$ hdfs dfs -chown ronaldo:ronaldo /user/ronaldo
[hdfs@ip-172-31-5-225 ~]$ hdfs dfs -chown neymar:neymar /user/neymar
```

## Output
```
[hdfs@ip-172-31-5-225 ~]$ hdfs dfs -ls /user/
Found 6 items
drwxrwxrwx   - mapred  hadoop           0 2017-03-10 10:00 /user/history
drwxrwxr-t   - hive    hive             0 2017-03-10 10:00 /user/hive
drwxrwxr-x   - hue     hue              0 2017-03-10 10:01 /user/hue
drwxr-xr-x   - neymar  neymar           0 2017-03-10 10:10 /user/neymar
drwxrwxr-x   - oozie   oozie            0 2017-03-10 10:01 /user/oozie
drwxr-xr-x   - ronaldo ronaldo          0 2017-03-10 10:11 /user/ronaldo
```


## API output


`http://ec2-52-42-83-199.us-west-2.compute.amazonaws.com:7180/api/v14/hosts`

```
{
  "items" : [ {
    "hostId" : "58a578f3-2386-4cba-9574-35e1fbc4c4ec",
    "ipAddress" : "172.31.10.168",
    "hostname" : "ip-172-31-10-168.us-west-2.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-3-220.us-west-2.compute.internal:7180/cmf/hostRedirect/58a578f3-2386-4cba-9574-35e1fbc4c4ec",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 2,
    "totalPhysMemBytes" : 15331930112
  }, {
    "hostId" : "b57177ec-f6cc-47ab-9155-09d0ac256d99",
    "ipAddress" : "172.31.3.220",
    "hostname" : "ip-172-31-3-220.us-west-2.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-3-220.us-west-2.compute.internal:7180/cmf/hostRedirect/b57177ec-f6cc-47ab-9155-09d0ac256d99",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 2,
    "totalPhysMemBytes" : 15331930112
  }, {
    "hostId" : "cf55e617-686b-4498-a557-1f41506b6787",
    "ipAddress" : "172.31.5.180",
    "hostname" : "ip-172-31-5-180.us-west-2.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-3-220.us-west-2.compute.internal:7180/cmf/hostRedirect/cf55e617-686b-4498-a557-1f41506b6787",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 2,
    "totalPhysMemBytes" : 15331930112
  }, {
    "hostId" : "ef78641a-ded4-48cf-b02f-e0c385281f7b",
    "ipAddress" : "172.31.5.225",
    "hostname" : "ip-172-31-5-225.us-west-2.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-3-220.us-west-2.compute.internal:7180/cmf/hostRedirect/ef78641a-ded4-48cf-b02f-e0c385281f7b",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 2,
    "totalPhysMemBytes" : 15331930112
  }, {
    "hostId" : "6d56e0cf-59c2-4174-8126-045ceb015b8e",
    "ipAddress" : "172.31.9.26",
    "hostname" : "ip-172-31-9-26.us-west-2.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-3-220.us-west-2.compute.internal:7180/cmf/hostRedirect/6d56e0cf-59c2-4174-8126-045ceb015b8e",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 2,
    "totalPhysMemBytes" : 15331930112
  } ]
}
```
