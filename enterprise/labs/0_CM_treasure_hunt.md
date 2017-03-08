### 1. What is ubertask optimization?

Runs "sufficiently small" jobs sequentially within a single JVM. "Small" is defined by the mapreduce.job.ubertask.maxmaps, mapreduce.job.ubertask.maxreduces, and mapreduce.job.ubertask.maxbytes settings.

`mapreduce.job.ubertask.enable = false (default)`


### 2. Where in CM is the Kerberos Security Realm value displayed?

Administration -> Settings -> Kerberos ->
Kerberos Security Realm


### 3. Which CDH service(s) host a property for enabling Kerberos authentication?





### 4. How do you upgrade the CM agents?

- Stop services like Hive and Oozie
- On the node which runs cloudera manager server, stop the server, agent and database
- Make sure you have the cloudera yum repository setup in /etc/yum.repos.d with the latest version
- Upgrade the cloudera manager server
  - yum clean all
  - yum update cloudera-manager-server cloudera-manager-daemons cloudera-manager-server-db-2 cloudera-manager-agent
- Start the database and the cloudera manager server
- Login to the cloudera manager web UI and follow the upgrade steps

Useful information: https://www.cloudera.com/documentation/enterprise/latest/topics/cm_ag_upgrading_cm.html



### 5. Give the tsquery statement used to chart Hue's CPU utilization?

`select cpu_user_rate where roleType=HUE_SERVER`


### 6. Name all the roles that make up the Hive service

Hive service:
* Hive Metastore Server
* WebHCat Server
* HiveServer2
* Gateway


### 7. What steps must be completed before integrating Cloudera Manager with Kerberos?

* Verify User Accounts and Groups in CDH 5 Due to Security
* If you are Using AES-256 Encryption, Install the JCE Policy File
* Create and Deploy the Kerberos Principals and Keytab Files
* Shut Down the Cluster
* Enable Hadoop Security
* Configure Secure HDFS
* Configuring Security for HDFS High Availability
* Configure secure WebHDFS
* Configuring a secure HDFS NFS Gateway
* Set Variables for Secure DataNodes
* Start up the NameNode
* Start up a DataNode
* Set the Sticky Bit on HDFS Directories
* Start up the Secondary NameNode (if used)
* Configure Either MRv1 Security or YARN Security
