# mariadb

> yum install -y mariadb-server

> systemctl statys mariadb

> systemctl start mariadb

> mysql_secure_installation

[root@localhost centos-use]# mysql_secure_installation 

NOTE: RUNNING ALL PARTS OF THIS SCRIPT IS RECOMMENDED FOR ALL MariaDB
      SERVERS IN PRODUCTION USE!  PLEASE READ EACH STEP CAREFULLY!

In order to log into MariaDB to secure it, we'll need the current
password for the root user.  If you've just installed MariaDB, and
you haven't set the root password yet, the password will be blank,
so you should just press enter here.

Enter current password for root (enter for none): 
ERROR 1045 (28000): Access denied for user 'root'@'localhost' (using password: YES)
Enter current password for root (enter for none): 
ERROR 1045 (28000): Access denied for user 'root'@'localhost' (using password: YES)
Enter current password for root (enter for none): 
OK, successfully used password, moving on...

Setting the root password ensures that nobody can log into the MariaDB
root user without the proper authorisation.

Set root password? [Y/n] y
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

Remove anonymous users? [Y/n] y
 ... Success!

Normally, root should only be allowed to connect from 'localhost'.  This
ensures that someone cannot guess at the root password from the network.

Disallow root login remotely? [Y/n] n
 ... skipping.

By default, MariaDB comes with a database named 'test' that anyone can
access.  This is also intended only for testing, and should be removed
before moving into a production environment.

Remove test database and access to it? [Y/n] n
 ... skipping.

Reloading the privilege tables will ensure that all changes made so far
will take effect immediately.

Reload privilege tables now? [Y/n] y
 ... Success!

Cleaning up...

All done!  If you've completed all of the above steps, your MariaDB
installation should now be secure.

Thanks for using MariaDB!
[root@localhost centos-use]# systemctl restart mariadb 

[root@localhost centos-use]# mysql -uroot -proot
Welcome to the MariaDB monitor.  Commands end with ; or \g.
Your MariaDB connection id is 2
Server version: 5.5.60-MariaDB MariaDB Server

Copyright (c) 2000, 2018, Oracle, MariaDB Corporation Ab and others.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

MariaDB [(none)]> use test
Database changed
MariaDB [test]> show tables;
Empty set (0.00 sec)

MariaDB [test]> create table ac01(aac001 integer primary key auto_increment, aac002 varchar(32) not null default '');
Query OK, 0 rows affected (0.84 sec)

MariaDB [test]> show tables;
+----------------+
| Tables_in_test |
+----------------+
| ac01           |
+----------------+
1 row in set (0.00 sec)

MariaDB [test]> desc ac01;
+--------+-------------+------+-----+---------+----------------+
| Field  | Type        | Null | Key | Default | Extra          |
+--------+-------------+------+-----+---------+----------------+
| aac001 | int(11)     | NO   | PRI | NULL    | auto_increment |
| aac002 | varchar(32) | NO   |     |         |                |
+--------+-------------+------+-----+---------+----------------+
2 rows in set (0.00 sec)

MariaDB [test]> insert into ac01(aac002) values ('zs');
Query OK, 1 row affected (0.19 sec)

MariaDB [test]> select * from ac01;
+--------+--------+
| aac001 | aac002 |
+--------+--------+
|      1 | zs     |
+--------+--------+
1 row in set (0.00 sec)

MariaDB [test]> 

