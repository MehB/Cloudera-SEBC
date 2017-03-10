### MariaDB YUM repository

```
[mariadb]
name = MariaDB
baseurl = http://yum.mariadb.org/5.5/centos7-amd64
gpgkey=https://yum.mariadb.org/RPM-GPG-KEY-MariaDB
gpgcheck=1
```

##### Update the Packages

`$ sudo yum update`


### MariaDB version

```
MariaDB [(none)]> SHOW VARIABLES LIKE "%version%";
+-------------------------+---------------------+
| Variable_name           | Value               |
+-------------------------+---------------------+
| innodb_version          | 5.5.52-MariaDB-38.3 |
| protocol_version        | 10                  |
| slave_type_conversions  |                     |
| version                 | 5.5.54-MariaDB      |
| version_comment         | MariaDB Server      |
| version_compile_machine | x86_64              |
| version_compile_os      | Linux               |
+-------------------------+---------------------+
7 rows in set (0.00 sec)
```


### Database Host Name

```
MariaDB [(none)]> select @@hostname;
+--------------------------------------------+
| @@hostname                                 |
+--------------------------------------------+
| ip-172-31-5-225.us-west-2.compute.internal |
+--------------------------------------------+
1 row in set (0.00 sec)
```

### List of Databases

```
MariaDB [(none)]> show databases;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| hive               |
| hue                |
| mysql              |
| oozie              |
| performance_schema |
| rman               |
| scm                |
| sentry             |
+--------------------+
9 rows in set (0.00 sec)
```
