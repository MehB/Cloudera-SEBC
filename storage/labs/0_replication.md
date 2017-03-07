1. Generate 500MB with teragen:

`[hadoop01@ip-172-31-14-88 ~]$ hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar teragen 500000 /user/hadoop01/teragen-data_500MB`


2. Copy the file from Edge node to Name node:

`hadoop distcp hdfs://ip-172-31-14-88.us-west-2.compute.internal/user/hadoop01/teragen-data hdfs://ip-172-31-16-8.us-west-2.compute.internal/user/hadoop01/copy_file/`


3. Browse the results:

```
hdfs fsck /user/hadoop01/teragen-data -files -blocks
Connecting to namenode via http://ip-172-31-16-8.us-west-2.compute.internal:50070
FSCK started by root (auth:SIMPLE) from /172.31.16.8 for path /user/hadoop01/teragen-data at Tue Mar 07 20:38:27 UTC 2017
/user/hadoop01/teragen-data <dir>
/user/hadoop01/teragen-data/_SUCCESS 0 bytes, 0 block(s):  OK

/user/hadoop01/teragen-data/part-m-00000 2500000 bytes, 1 block(s):  OK
0. BP-108507781-172.31.16.8-1488889598070:blk_1073744523_3699 len=2500000 Live_repl=3

/user/hadoop01/teragen-data/part-m-00001 2500000 bytes, 1 block(s):  OK
0. BP-108507781-172.31.16.8-1488889598070:blk_1073744524_3700 len=2500000 Live_repl=3

Status: HEALTHY
 Total size:	5000000 B
 Total dirs:	1
 Total files:	3
 Total symlinks:		0
 Total blocks (validated):	2 (avg. block size 2500000 B)
 Minimally replicated blocks:	2 (100.0 %)
 Over-replicated blocks:	0 (0.0 %)
 Under-replicated blocks:	0 (0.0 %)
 Mis-replicated blocks:		0 (0.0 %)
 Default replication factor:	3
 Average block replication:	3.0
 Corrupt blocks:		0
 Missing replicas:		0 (0.0 %)
 Number of data-nodes:		3
 Number of racks:		1
FSCK ended at Tue Mar 07 20:38:27 UTC 2017 in 1 milliseconds


The filesystem under path '/user/hadoop01/teragen-data' is HEALTHY
```
