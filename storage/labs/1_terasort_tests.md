1. Create the user and the hdfs home directory for this user + add permissions:

`user = hadoop01`

```
[root@ip-172-31-16-8 ~]# hdfs dfs -ls /user/
Found 7 items
drwxr-xr-x   - admin    admin               0 2017-03-07 13:42 /user/admin
drwxr-xr-x   - hadoop01 supergroup          0 2017-03-07 20:30 /user/hadoop01
...
```

2. Create a 10GB file using `teragen`

`time hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar teragen -Dmapreduce.job.maps=4 -Ddfs.block.size=33554432  100000000 /user/hadoop01/benchhmark/terasort-input`

Result:
```
17/03/07 21:04:04 INFO mapreduce.Job: Counters: 31
	File System Counters
		FILE: Number of bytes read=0
		FILE: Number of bytes written=488424
		FILE: Number of read operations=0
		FILE: Number of large read operations=0
		FILE: Number of write operations=0
		HDFS: Number of bytes read=344
		HDFS: Number of bytes written=10000000000
		HDFS: Number of read operations=16
		HDFS: Number of large read operations=0
		HDFS: Number of write operations=8
	Job Counters
		Launched map tasks=4
		Other local map tasks=4
		Total time spent by all maps in occupied slots (ms)=543436
		Total time spent by all reduces in occupied slots (ms)=0
		Total time spent by all map tasks (ms)=543436
		Total vcore-seconds taken by all map tasks=543436
		Total megabyte-seconds taken by all map tasks=556478464
	Map-Reduce Framework
		Map input records=100000000
		Map output records=100000000
		Input split bytes=344
		Spilled Records=0
		Failed Shuffles=0
		Merged Map outputs=0
		GC time elapsed (ms)=2011
		CPU time spent (ms)=159060
		Physical memory (bytes) snapshot=786776064
		Virtual memory (bytes) snapshot=6276046848
		Total committed heap usage (bytes)=799539200
	org.apache.hadoop.examples.terasort.TeraGen$Counters
		CHECKSUM=214760662691937609
	File Input Format Counters
		Bytes Read=0
	File Output Format Counters
		Bytes Written=10000000000

real	2m30.277s
user	0m6.028s
sys	0m0.683s
```

Terasort:

`time hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar terasort -Dmapreduce.job.maps=4 -Ddfs.block.size=33554432 /user/hadoop01/benchhmark/terasort-input /user/hadoop01/benchhmark/terasort-output`

Result:

```
17/03/07 21:22:46 INFO mapreduce.Job: Job job_1488899004846_0035 completed successfully
17/03/07 21:22:46 INFO mapreduce.Job: Counters: 49
	File System Counters
		FILE: Number of bytes read=4476205629
		FILE: Number of bytes written=8889206680
		FILE: Number of read operations=0
		FILE: Number of large read operations=0
		FILE: Number of write operations=0
		HDFS: Number of bytes read=10000051300
		HDFS: Number of bytes written=10000000000
		HDFS: Number of read operations=918
		HDFS: Number of large read operations=0
		HDFS: Number of write operations=12
	Job Counters
		Launched map tasks=300
		Launched reduce tasks=6
		Data-local map tasks=300
		Total time spent by all maps in occupied slots (ms)=2443774
		Total time spent by all reduces in occupied slots (ms)=649218
		Total time spent by all map tasks (ms)=2443774
		Total time spent by all reduce tasks (ms)=649218
		Total vcore-seconds taken by all map tasks=2443774
		Total vcore-seconds taken by all reduce tasks=649218
		Total megabyte-seconds taken by all map tasks=2502424576
		Total megabyte-seconds taken by all reduce tasks=664799232
	Map-Reduce Framework
		Map input records=100000000
		Map output records=100000000
		Map output bytes=10200000000
		Map output materialized bytes=4375170195
		Input split bytes=51300
		Combine input records=0
		Combine output records=0
		Reduce input groups=100000000
		Reduce shuffle bytes=4375170195
		Reduce input records=100000000
		Reduce output records=100000000
		Spilled Records=200000000
		Shuffled Maps =1800
		Failed Shuffles=0
		Merged Map outputs=1800
		GC time elapsed (ms)=30334
		CPU time spent (ms)=1441990
		Physical memory (bytes) snapshot=146513166336
		Virtual memory (bytes) snapshot=481251917824
		Total committed heap usage (bytes)=173239959552
	Shuffle Errors
		BAD_ID=0
		CONNECTION=0
		IO_ERROR=0
		WRONG_LENGTH=0
		WRONG_MAP=0
		WRONG_REDUCE=0
	File Input Format Counters
		Bytes Read=10000000000
	File Output Format Counters
		Bytes Written=10000000000
17/03/07 21:22:46 INFO terasort.TeraSort: done

real	7m47.193s
user	0m9.673s
sys	0m0.933s
```



Useful information: (https://gist.github.com/ace-subido/0a9b219b2348921f6a87)
