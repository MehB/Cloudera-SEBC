### Cloud Provider:

* AWS



### Node IP and DNS

| Name  | Private DNS | Private IP |
| ------------- | ------------- | ------------- |
| Cloudera manager | ec2-52-41-186-187.us-west-2.compute.amazonaws.com |52.41.186.187 |
| Master  | ec2-52-42-83-199.us-west-2.compute.amazonaws.com  |52.42.83.199  |
| Worker  | ec2-35-163-78-230.us-west-2.compute.amazonaws.com |35.163.78.230 |
| Worker | ec2-35-164-44-247.us-west-2.compute.amazonaws.com |35.164.44.247  |
| Worker  | ec2-52-33-157-106.us-west-2.compute.amazonaws.com  |52.33.157.106 |


### Linux version

```
$ cat /etc/*release
CentOS Linux release 7.3.1611 (Core)
NAME="CentOS Linux"
VERSION="7 (Core)"
ID="centos"
ID_LIKE="rhel fedora"
VERSION_ID="7"
PRETTY_NAME="CentOS Linux 7 (Core)"
```

### Disk space

```
$ df -h
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvda1       50G  1.7G   49G   4% /
devtmpfs        7.3G     0  7.3G   0% /dev
tmpfs           7.2G     0  7.2G   0% /dev/shm
tmpfs           7.2G   17M  7.2G   1% /run
tmpfs           7.2G     0  7.2G   0% /sys/fs/cgroup
tmpfs           1.5G     0  1.5G   0% /run/user/1000
tmpfs           1.5G     0  1.5G   0% /run/user/0
```

### Repo List

```
$ yum repolist enabled
Loaded plugins: fastestmirror
Loading mirror speeds from cached hostfile
 * base: mirrors.cat.pdx.edu
 * extras: mirrors.kernel.org
 * updates: mirrors.ocf.berkeley.edu
repo id                                                                                                            repo name                                                                                                            status
base/7/x86_64                                                                                                      CentOS-7 - Base                                                                                                      9,363
extras/7/x86_64                                                                                                    CentOS-7 - Extras                                                                                                      311
updates/7/x86_64                                                                                                   CentOS-7 - Updates                                                                                                   1,107
repolist: 10,781
```


### Users and groups creation

```
neymar:x:2010:2010::/home/neymar:/bin/bash
ronaldo:x:2016:2016::/home/ronaldo:/bin/bash
```

```
barca:x:1001:ronaldo
merengues:x:1002:neymar

```
