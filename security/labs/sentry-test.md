###### 1. Connect to Hive with beeline:

```
beeline> !connect jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-14-88.us-west-2.compute.internal@MEHB.COM
scan complete in 4ms
Connecting to jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-14-88.us-west-2.compute.internal@MEHB.COM
Enter username for jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-14-88.us-west-2.compute.internal@MEHB.COM: hadoop01
Enter password for jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-14-88.us-west-2.compute.internal@MEHB.COM: *******
Connected to: Apache Hive (version 1.1.0-cdh5.8.3)
Driver: Hive JDBC (version 1.1.0-cdh5.8.3)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://localhost:10000/default> show tables;
INFO  : Compiling command(queryId=hive_20170309094646_d4b87230-4577-4abd-9e04-07624b2fb331): show tables
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20170309094646_d4b87230-4577-4abd-9e04-07624b2fb331); Time taken: 0.744 seconds
INFO  : Executing command(queryId=hive_20170309094646_d4b87230-4577-4abd-9e04-07624b2fb331): show tables
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170309094646_d4b87230-4577-4abd-9e04-07624b2fb331); Time taken: 0.265 seconds
INFO  : OK
+-----------+--+
| tab_name  |
+-----------+--+
+-----------+--+
No rows selected (2.355 seconds)
```



###### 2.

```
0: jdbc:hive2://localhost:10000/default> CREATE ROLE sentry_admin;
INFO  : Compiling command(queryId=hive_20170309095353_2d3713c3-bf75-45b3-b31a-ab9ec83483a3): CREATE ROLE sentry_admin
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20170309095353_2d3713c3-bf75-45b3-b31a-ab9ec83483a3); Time taken: 0.084 seconds
INFO  : Executing command(queryId=hive_20170309095353_2d3713c3-bf75-45b3-b31a-ab9ec83483a3): CREATE ROLE sentry_admin
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170309095353_2d3713c3-bf75-45b3-b31a-ab9ec83483a3); Time taken: 0.796 seconds
INFO  : OK
No rows affected (0.892 seconds)
```

```
0: jdbc:hive2://localhost:10000/default> GRANT ALL ON SERVER server1 TO ROLE sentry_admin;
INFO  : Compiling command(queryId=hive_20170309100303_65ad904c-f912-4656-9424-3aaea8ebb305): GRANT ALL ON SERVER server1 TO ROLE sentry_admin
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20170309100303_65ad904c-f912-4656-9424-3aaea8ebb305); Time taken: 0.092 seconds
INFO  : Executing command(queryId=hive_20170309100303_65ad904c-f912-4656-9424-3aaea8ebb305): GRANT ALL ON SERVER server1 TO ROLE sentry_admin
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170309100303_65ad904c-f912-4656-9424-3aaea8ebb305); Time taken: 0.112 seconds
INFO  : OK
No rows affected (0.285 seconds)
```

```
0: jdbc:hive2://localhost:10000/default> GRANT ROLE sentry_admin TO GROUP hadoop01;
INFO  : Compiling command(queryId=hive_20170309100404_ef0d1a2d-246f-4974-88cd-33c1fecbbd36): GRANT ROLE sentry_admin TO GROUP hadoop01
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20170309100404_ef0d1a2d-246f-4974-88cd-33c1fecbbd36); Time taken: 0.059 seconds
INFO  : Executing command(queryId=hive_20170309100404_ef0d1a2d-246f-4974-88cd-33c1fecbbd36): GRANT ROLE sentry_admin TO GROUP hadoop01
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170309100404_ef0d1a2d-246f-4974-88cd-33c1fecbbd36); Time taken: 0.074 seconds
INFO  : OK
No rows affected (0.142 seconds)
```

```
0: jdbc:hive2://localhost:10000/default> SHOW TABLES;
INFO  : Compiling command(queryId=hive_20170309100404_b7749357-f54d-4338-8e49-151ec0654e15): SHOW TABLES
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20170309100404_b7749357-f54d-4338-8e49-151ec0654e15); Time taken: 0.086 seconds
INFO  : Executing command(queryId=hive_20170309100404_b7749357-f54d-4338-8e49-151ec0654e15): SHOW TABLES
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170309100404_b7749357-f54d-4338-8e49-151ec0654e15); Time taken: 0.163 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| customers  |
| sample_07  |
| sample_08  |
| web_logs   |
+------------+--+
4 rows selected (0.354 seconds)
```

###### --> Now I see all my tables  



###### 2. New user creation + kerberos add principal

```
# kadmin.local
Authenticating as principal hadoop01/admin@MEHB.COM with password.
kadmin.local:  add_principal george
WARNING: no policy specified for george@MEHB.COM; defaulting to no policy
Enter password for principal "george@MEHB.COM":
Re-enter password for principal "george@MEHB.COM":
Principal "george@MEHB.COM" created.
kadmin.local:  add_principal ferdinand
WARNING: no policy specified for ferdinand@MEHB.COM; defaulting to no policy
Enter password for principal "ferdinand@MEHB.COM":
Re-enter password for principal "ferdinand@MEHB.COM":
Principal "ferdinand@MEHB.COM" created.
kadmin.local:  quit
```

###### Create role:
```
CREATE ROLE reads;
INFO  : Compiling command(queryId=hive_20170309111010_d973866f-17fb-4411-bd97-a926a4c0b258): CREATE ROLE reads
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20170309111010_d973866f-17fb-4411-bd97-a926a4c0b258); Time taken: 0.069 seconds
INFO  : Executing command(queryId=hive_20170309111010_d973866f-17fb-4411-bd97-a926a4c0b258): CREATE ROLE reads
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170309111010_d973866f-17fb-4411-bd97-a926a4c0b258); Time taken: 0.041 seconds
INFO  : OK
No rows affected (0.19 seconds)
```

###### Create role
```
CREATE ROLE writes;
INFO  : Compiling command(queryId=hive_20170309111111_01eac13f-00ab-4a96-a063-9da9fe9dd28a): CREATE ROLE writes
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20170309111111_01eac13f-00ab-4a96-a063-9da9fe9dd28a); Time taken: 0.101 seconds
INFO  : Executing command(queryId=hive_20170309111111_01eac13f-00ab-4a96-a063-9da9fe9dd28a): CREATE ROLE writes
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170309111111_01eac13f-00ab-4a96-a063-9da9fe9dd28a); Time taken: 0.026 seconds
INFO  : OK
No rows affected (0.141 seconds)
```

###### Grant read privilege for all tables to `reads`
```
GRANT SELECT ON DATABASE default TO ROLE reads;
INFO  : Compiling command(queryId=hive_20170309111111_57205b34-62bf-466c-b13e-52c63588c798): GRANT SELECT ON DATABASE default TO ROLE reads
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20170309111111_57205b34-62bf-466c-b13e-52c63588c798); Time taken: 0.071 seconds
INFO  : Executing command(queryId=hive_20170309111111_57205b34-62bf-466c-b13e-52c63588c798): GRANT SELECT ON DATABASE default TO ROLE reads
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170309111111_57205b34-62bf-466c-b13e-52c63588c798); Time taken: 0.041 seconds
INFO  : OK
No rows affected (0.12 seconds)
0: jdbc:hive2://localhost:10000/default> GRANT ROLE reads TO GROUP selector;
INFO  : Compiling command(queryId=hive_20170309111111_2af221bf-fcbc-4e9f-b4c9-14b66286036c): GRANT ROLE reads TO GROUP selector
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20170309111111_2af221bf-fcbc-4e9f-b4c9-14b66286036c); Time taken: 0.057 seconds
INFO  : Executing command(queryId=hive_20170309111111_2af221bf-fcbc-4e9f-b4c9-14b66286036c): GRANT ROLE reads TO GROUP selector
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170309111111_2af221bf-fcbc-4e9f-b4c9-14b66286036c); Time taken: 0.028 seconds
INFO  : OK
No rows affected (0.093 seconds)
```


###### Grant read privilege for default.sample07 only to 'writes':

```
REVOKE ALL ON DATABASE default FROM ROLE writes;
INFO  : Compiling command(queryId=hive_20170309111313_96fc86e8-2c87-49a2-8470-17b62bad9865): REVOKE ALL ON DATABASE default FROM ROLE writes
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20170309111313_96fc86e8-2c87-49a2-8470-17b62bad9865); Time taken: 0.057 seconds
INFO  : Executing command(queryId=hive_20170309111313_96fc86e8-2c87-49a2-8470-17b62bad9865): REVOKE ALL ON DATABASE default FROM ROLE writes
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170309111313_96fc86e8-2c87-49a2-8470-17b62bad9865); Time taken: 0.09 seconds
INFO  : OK
No rows affected (0.16 seconds)
0: jdbc:hive2://localhost:10000/default> GRANT SELECT ON default.sample_07 TO ROLE writes;
INFO  : Compiling command(queryId=hive_20170309111313_58d17a53-469a-4f7b-9298-f239360ceb32): GRANT SELECT ON default.sample_07 TO ROLE writes
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20170309111313_58d17a53-469a-4f7b-9298-f239360ceb32); Time taken: 0.056 seconds
INFO  : Executing command(queryId=hive_20170309111313_58d17a53-469a-4f7b-9298-f239360ceb32): GRANT SELECT ON default.sample_07 TO ROLE writes
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170309111313_58d17a53-469a-4f7b-9298-f239360ceb32); Time taken: 0.037 seconds
INFO  : OK
No rows affected (0.103 seconds)
0: jdbc:hive2://localhost:10000/default> GRANT ROLE writes TO GROUP inserters;
INFO  : Compiling command(queryId=hive_20170309111313_b0d14e0d-cf81-4009-af88-010f610205b3): GRANT ROLE writes TO GROUP inserters
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20170309111313_b0d14e0d-cf81-4009-af88-010f610205b3); Time taken: 0.055 seconds
INFO  : Executing command(queryId=hive_20170309111313_b0d14e0d-cf81-4009-af88-010f610205b3): GRANT ROLE writes TO GROUP inserters
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170309111313_b0d14e0d-cf81-4009-af88-010f610205b3); Time taken: 0.028 seconds
INFO  : OK
No rows affected (0.091 seconds)
```


###### kinit as georges and beeline connection:
```
# kinit george@MEHB.COM
Password for george@MEHB.COM:
```

```
Connecting to jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-14-88.us-west-2.compute.internal@MEHB.COM
Enter username for jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-14-88.us-west-2.compute.internal@MEHB.COM: george
Enter password for jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-14-88.us-west-2.compute.internal@MEHB.COM: *******
....
show tables;
INFO  : Compiling command(queryId=hive_20170309112525_549b7b08-16eb-4459-b335-d785cc3a2d92): show tables
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20170309112525_549b7b08-16eb-4459-b335-d785cc3a2d92); Time taken: 0.072 seconds
INFO  : Executing command(queryId=hive_20170309112525_549b7b08-16eb-4459-b335-d785cc3a2d92): show tables
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170309112525_549b7b08-16eb-4459-b335-d785cc3a2d92); Time taken: 0.14 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| customers  |
| sample_07  |
| sample_08  |
| web_logs   |
+------------+--+
4 rows selected (0.349 seconds)
```

####### Same procedure for Ferdinand:

```
show tables
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20170309112727_e62e7aed-0d3a-41d6-812b-7946cef6aa0e); Time taken: 0.07 seconds
INFO  : Executing command(queryId=hive_20170309112727_e62e7aed-0d3a-41d6-812b-7946cef6aa0e): show tables
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170309112727_e62e7aed-0d3a-41d6-812b-7946cef6aa0e); Time taken: 0.162 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| sample_07  |
+------------+--+
1 row selected (0.358 seconds)
```
