###### 1. Connect to Hive with beeline:

```
show tables;
INFO  : Compiling command(queryId=hive_20170308202828_8c63a250-f01a-4ba8-926b-a31d8d774c13): show tables
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20170308202828_8c63a250-f01a-4ba8-926b-a31d8d774c13); Time taken: 0.003 seconds
INFO  : Executing command(queryId=hive_20170308202828_8c63a250-f01a-4ba8-926b-a31d8d774c13): show tables
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170308202828_8c63a250-f01a-4ba8-926b-a31d8d774c13); Time taken: 0.014 seconds
INFO  : OK
+-----------+--+
| tab_name  |
+-----------+--+
+-----------+--+
No rows selected (0.028 seconds)
```



###### 2. 
