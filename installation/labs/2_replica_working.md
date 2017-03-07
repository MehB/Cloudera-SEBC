MySQL Installation:


4.

```
Setting the root password ensures that nobody can log into the MariaDB
root user without the proper authorisation.

Set root password? [Y/n] Y
New password:
Re-enter new password:
Password updated successfully!
Reloading privilege tables..
 ... Success!


By default, a MariaDB installation has an anonymous user, allowing anyone
to log into MariaDB without having to have a user account created for
them.  This is intended only for testing, and to make the installation
go a bit smoother.  You should remove them before moving into a
production environment.

Remove anonymous users? [Y/n] Y
 ... Success!

Normally, root should only be allowed to connect from 'localhost'.  This
ensures that someone cannot guess at the root password from the network.

Disallow root login remotely? [Y/n] N
 ... Success!

By default, MariaDB comes with a database named 'test' that anyone can
access.  This is also intended only for testing, and should be removed
before moving into a production environment.

Remove test database and access to it? [Y/n] Y
 - Dropping test database...
 ... Success!
 - Removing privileges on test database...
 ... Success!

Reloading the privilege tables will ensure that all changes made so far
will take effect immediately.

Reload privilege tables now? [Y/n] Y
 ... Success!

Cleaning up...

All done!  If you've completed all of the above steps, your MariaDB
installation should now be secure.

Thanks for using MariaDB!
```


5.

```
MariaDB [(none)]> GRANT REPLICATION SLAVE ON *.* TO 'node01'@'ip-172-31-16-8' IDENTIFIED BY 'manager';
Query OK, 0 rows affected (0.00 sec)

MariaDB [(none)]> SET GLOBAL binlog_format = 'ROW';
Query OK, 0 rows affected (0.00 sec)

MariaDB [(none)]> FLUSH TABLES WITH READ LOCK;
Query OK, 0 rows affected (0.00 sec)

```

6.

```
MariaDB [(none)]> SHOW MASTER STATUS;
+-------------------------+----------+--------------+------------------+
| File                    | Position | Binlog_Do_DB | Binlog_Ignore_DB |
+-------------------------+----------+--------------+------------------+
| mysql_binary_log.000005 |      403 |              |                  |
+-------------------------+----------+--------------+------------------+
1 row in set (0.00 sec)

MariaDB [(none)]> UNLOCK TABLES;
Query OK, 0 rows affected (0.00 sec)
```


7.
```
MariaDB [(none)]> CHANGE MASTER TO MASTER_HOST='ip-172-31-14-88.us-west-2.compute.internal', MASTER_USER='node01', MASTER_PASSWORD='manager', MASTER_LOG_FILE='mysql_binary_log.000010', MASTER_LOG_POS=430;
Query OK, 0 rows affected (0.01 sec)

MariaDB [(none)]> START SLAVE;
Query OK, 0 rows affected (0.00 sec)
```

8.

```
MariaDB [(none)]> SHOW SLAVE STATUS \G
*************************** 1. row ***************************
               Slave_IO_State: Waiting for master to send event
                  Master_Host: ip-172-31-14-88.us-west-2.compute.internal
                  Master_User: node01
                  Master_Port: 3306
                Connect_Retry: 60
              Master_Log_File: mysql_binary_log.000010
          Read_Master_Log_Pos: 430
               Relay_Log_File: ip-172-31-16-8-relay-bin.000002
                Relay_Log_Pos: 536
        Relay_Master_Log_File: mysql_binary_log.000010
             Slave_IO_Running: Yes
            Slave_SQL_Running: Yes
              Replicate_Do_DB:
          Replicate_Ignore_DB:
           Replicate_Do_Table:
       Replicate_Ignore_Table:
      Replicate_Wild_Do_Table:
  Replicate_Wild_Ignore_Table:
                   Last_Errno: 0
                   Last_Error:
                 Skip_Counter: 0
          Exec_Master_Log_Pos: 430
              Relay_Log_Space: 839
              Until_Condition: None
               Until_Log_File:
                Until_Log_Pos: 0
           Master_SSL_Allowed: No
           Master_SSL_CA_File:
           Master_SSL_CA_Path:
              Master_SSL_Cert:
            Master_SSL_Cipher:
               Master_SSL_Key:
        Seconds_Behind_Master: 0
Master_SSL_Verify_Server_Cert: No
                Last_IO_Errno: 0
                Last_IO_Error:
               Last_SQL_Errno: 0
               Last_SQL_Error:
  Replicate_Ignore_Server_Ids:
             Master_Server_Id: 2
1 row in set (0.00 sec)
```


9. Create Databases and users:

```
MariaDB [(none)]> create database amon DEFAULT CHARACTER SET utf8;
ERROR 1007 (HY000): Can't create database 'amon'; database exists
MariaDB [(none)]>
MariaDB [(none)]>
MariaDB [(none)]>
MariaDB [(none)]> grant all on amon.* TO 'amon'@'%' IDENTIFIED BY 'amon_password';
Query OK, 0 rows affected (0.00 sec)

MariaDB [(none)]>
MariaDB [(none)]>
MariaDB [(none)]>
MariaDB [(none)]> create database rman DEFAULT CHARACTER SET utf8;
Query OK, 1 row affected (0.00 sec)

MariaDB [(none)]> grant all on rman.* TO 'rman'@'%' IDENTIFIED BY 'rman_password';
Query OK, 0 rows affected (0.00 sec)

MariaDB [(none)]> create database metastore DEFAULT CHARACTER SET utf8;
Query OK, 1 row affected (0.00 sec)

MariaDB [(none)]> grant all on metastore.* TO 'hive'@'%' IDENTIFIED BY 'hive_password';
Query OK, 0 rows affected (0.00 sec)

MariaDB [(none)]> create database sentry DEFAULT CHARACTER SET utf8;
Query OK, 1 row affected (0.00 sec)

MariaDB [(none)]> grant all on sentry.* TO 'sentry'@'%' IDENTIFIED BY 'sentry_password';
Query OK, 0 rows affected (0.00 sec)

MariaDB [(none)]> create database nav DEFAULT CHARACTER SET utf8;
Query OK, 1 row affected (0.00 sec)

MariaDB [(none)]> grant all on nav.* TO 'nav'@'%' IDENTIFIED BY 'nav_password';
Query OK, 0 rows affected (0.00 sec)

MariaDB [(none)]> create database navms DEFAULT CHARACTER SET utf8;
Query OK, 1 row affected (0.00 sec)

MariaDB [(none)]> grant all on navms.* TO 'navms'@'%' IDENTIFIED BY 'navms_password';
Query OK, 0 rows affected (0.00 sec)
```

- Create Databases for Hue and Oozie:

```
create database oozie DEFAULT CHARACTER SET utf8;
grant all privileges on oozie.* to 'oozie'@'%' identified by 'oozie';

create database hue DEFAULT CHARACTER SET utf8;
grant all on hue.* to 'hue'@'%' identified by 'hue';
```
