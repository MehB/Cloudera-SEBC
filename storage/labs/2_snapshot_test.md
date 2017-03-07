Important: I create my user before seeing the instructions. Note that my user hdfs doesn't match to my GitHub handle.
hdfs user = hadoop01 

1. Create a `precious` directory in HDFS:

`hdfs dfs -mkdir /user/hadoop01/precious`


2. Copy the file (zip) and check it:

```
[hadoop01@ip-172-31-14-88 ~]$ hdfs dfs -ls /user/hadoop01/precious/
Found 1 items
drwxr-xr-x   - hadoop01 supergroup          0 2017-03-07 21:37 /user/hadoop01/precious/SEBC
```

3. Enable snapshots and create a snapshot called `sebc-hdfs-test`

4. Delete the directory:

Neither HDFS superuser nor the owner of the dataset can remove the snapshottable directory

5. Delete the File:

```
$ hdfs dfs -rm -r /user/hadoop01/precious/SEBC
17/03/07 21:50:00 INFO fs.TrashPolicyDefault: Moved: 'hdfs://ip-172-31-16-8.us-west-2.compute.internal:8020/user/hadoop01/precious/SEBC' to trash at: hdfs://ip-172-31-16-8.us-west-2.compute.internal:8020/user/hadoop01/.Trash/Current/user/hadoop01/precious/SEBC
```

6. Restore from snapshot:

Check if snapshot `sebc-hdfs-test` exists:

```
[hadoop01@ip-172-31-14-88 ~]$ hdfs dfs -ls /user/hadoop01/precious/.snapshot
Found 1 items
drwxr-xr-x   - hadoop01 supergroup          0 2017-03-07 21:41 /user/hadoop01/precious/.snapshot/sebc-hdfs-test
```

Restore procedure = Copy from snapshot directory to `precious` directory:

```
$ hdfs dfs -cp /user/hadoop01/precious/.snapshot/sebc-hdfs-test /user/hadoop01/precious/
[hadoop01@ip-172-31-14-88 ~]$ hdfs dfs -ls /user/hadoop01/precious/
Found 1 items
drwxr-xr-x   - hadoop01 supergroup          0 2017-03-07 21:59 /user/hadoop01/precious/sebc-hdfs-test
```
