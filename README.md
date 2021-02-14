# Test_Django

## running project

```script
python3 manage.py runserver 8080
```

## Creating the Polls app

```script
python3 manage.py startapp polls
```

## db migration

```script
python3 manage.py migrate
```

init tables이 만들어진다.

```mysql
[0:34][NamgiuicBookPro /usr/local/etc]
# mysql -uroot
Welcome to the MySQL monitor.  Commands end with ; or \g.
Your MySQL connection id is 26
Server version: 8.0.23 Homebrew

Copyright (c) 2000, 2021, Oracle and/or its affiliates.

Oracle is a registered trademark of Oracle Corporation and/or its
affiliates. Other names may be trademarks of their respective
owners.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

mysql> show databases
    -> ;
+---------------------+
| Database            |
+---------------------+
| costperinstallation |
| information_schema  |
| mysql               |
| performance_schema  |
| sys                 |
+---------------------+
5 rows in set (0.00 sec)

mysql> use costperinstallation
Reading table information for completion of table and column names
You can turn off this feature to get a quicker startup with -A

Database changed
mysql> show tables
    -> ;
+-------------------------------+
| Tables_in_costperinstallation |
+-------------------------------+
| auth_group                    |
| auth_group_permissions        |
| auth_permission               |
| auth_user                     |
| auth_user_groups              |
| auth_user_user_permissions    |
| django_admin_log              |
| django_content_type           |
| django_migrations             |
| django_session                |
+-------------------------------+
10 rows in set (0.00 sec)
```
