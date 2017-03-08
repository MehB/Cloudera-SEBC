
###### 1. Add the hadoop01 user to Kerberos:

```
# kadmin.local
Authenticating as principal cloudera-scm/admin@MEHB.COM with password.
kadmin.local:  addprinc hadoop01@MEHB.COM
WARNING: no policy specified for hadoop01@MEHB.COM; defaulting to no policy
Enter password for principal "hadoop01@MEHB.COM":
Re-enter password for principal "hadoop01@MEHB.COM":
Principal "hadoop01@MEHB.COM" created.
```

###### 2. Generate Keytab:

```
# ktutil
ktutil:  addent -password -p hadoop01@MEHB.COM -k 1 -e rc4-hmac
Password for hadoop01@MEHB.COM:
ktutil:  wkt hadoop01.keytab
ktutil:  quit
```

###### 3. Change permission and Connect to the user hadoop01

```
[root@ip-172-31-14-88 home]# chown hadoop01:hadoop01 hadoop01.keytab
[root@ip-172-31-14-88 home]#
[root@ip-172-31-14-88 home]# su - hadoop01
```

###### 4. `kinit` command  

`$ kinit hadoop01@MEHB.COM -k -t hadoop01.keytab`


###### 5. Output from the klist command:

`$ klist`

```
Ticket cache: FILE:/tmp/krb5cc_500
Default principal: hadoop01@MEHB.COM

Valid starting     Expires            Service principal
03/08/17 16:43:39  03/09/17 16:43:39  krbtgt/MEHB.COM@MEHB.COM
	renew until 03/15/17 16:43:39
```
