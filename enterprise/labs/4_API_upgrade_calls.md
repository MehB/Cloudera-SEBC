#### API part.

###### 1. API version:

version 14

`$ curl -u hadoop01:cloudera "http://52.35.67.233:7180/api/version"`


###### 2. Clouder Manager version:

```
$ curl -u hadoop01:cloudera "http://52.35.67.233:7180/api/v14/cm/version"
{
  "version" : "5.9.1",
  "buildUser" : "jenkins",
  "buildTimestamp" : "20170112-1158",
  "gitHash" : "a66d8bbdbe8bc3ee54235e55423f2f76c7d9f3b1",
  "snapshot" : false
}
```

###### 3. Cloudera Manager Users List:

```
$ curl -u hadoop01:cloudera "http://52.35.67.233:7180/api/v14/users"
{
  "items" : [ {
    "name" : "admin",
    "roles" : [ "ROLE_LIMITED" ]
  }, {
    "name" : "hadoop01",
    "roles" : [ "ROLE_ADMIN" ]
  }, {
    "name" : "minotaur",
    "roles" : [ "ROLE_CONFIGURATOR" ]
  } ]
}
```

###### 4. Report the database server in use by CM:

```
$ curl -u hadoop01:cloudera "http://52.35.67.233:7180/api/v14/cm/scmDbInfo"
{
  "scmDbType" : "MYSQL",
  "embeddedDbUsed" : false
}
```




#### Upgrade part.

###### 1. Stop the cluster

Cloudera Manager Admin Console -> Cluster -> Action -> Stop

###### 2. Stop the cloudera manager server agent:

```
[hadoop01@ip-172-31-14-88 ~]$ sudo service cloudera-scm-server status
[sudo] password for hadoop01:
cloudera-scm-server (pid  17852) is running...
[hadoop01@ip-172-31-14-88 ~]$ sudo service cloudera-scm-server stop
Stopping cloudera-scm-server:                              [  OK  ]
```


###### 3. If your cloudera manager host is running an agent, stop it:

```
[hadoop01@ip-172-31-14-88 ~]$ sudo service cloudera-scm-agent stop
Stopping cloudera-scm-agent:                               [  OK  ]
```


###### 4. Back up the following directories on the Cloudera Manager server host:

    * /etc/cloudera-scm-server
    * /etc/cloudera-scm-agent


###### 5. Update the cloudera-manager.repo file with the new version:

```
[cloudera-manager]
name = Cloudera Manager, Version 5.8.3
baseurl = https://archive.cloudera.com/cm5/redhat/6/x86_64/cm/5.9/
gpgkey = https://archive.cloudera.com/redhat/cdh/RPM-GPG-KEY-cloudera
gpgcheck = 1
```

###### 6. Clean and Upgrade:

```
sudo yum clean all
sudo yum upgrade cloudera-manager-server cloudera-manager-daemons cloudera-manager-agent
```


###### 7. Verify that your have the correct packages versions:

```
rpm -qa 'cloudera-manager-*'
cloudera-manager-daemons-5.9.1-1.cm591.p0.8.el6.x86_64
cloudera-manager-server-5.9.1-1.cm591.p0.8.el6.x86_64
cloudera-manager-agent-5.9.1-1.cm591.p0.8.el6.x86_64
```


###### 8. Start the cloudera manager server:

`sudo service cloudera-scm-server start`


###### 9. Login into clouder manager Admin Console:

Follow the wizard for upgrading, the cloudera manager.


###### 10. Restart the cluster when the upgrade process is finished


###### 11. Verify and Test the upgrade:


* Got to Hosts > All Hosts : OK
* Click the column header labeled "Last Heartbeat" to sort it : OK
* Verify that the last heartbeat for each host has occurred within one minute : OK
* Click on Host tab -> Inspect all hosts: OK
