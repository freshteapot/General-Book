#Install Percona

Replace mysql with Percona.

Follow their instructions for setting up the PPA.

##Setting up the config settings.

I have gone with adding a file to /etc/mysql/conf.d:

handlersocket.cnf

```
[mysqld]
loose_handlersocket_port = 9998
# the port number to bind to for read requests
loose_handlersocket_port_wr = 9999
# the port number to bind to for write requests
loose_handlersocket_threads = 16
# the number of worker threads for read requests
loose_handlersocket_threads_wr = 1
# the number of worker threads for write requests
open_files_limit = 65535
# to allow handlersocket to accept many concurrent
# connections, make open_files_limit as large as
# possible.
```

Server version: 5.5.24-55 Percona Server (GPL), Release 26.0

```
mysql> install plugin handlersocket soname 'handlersocket.so';
Query OK, 0 rows affected (0.34 sec)
```

##Links

* http://www.percona.com/doc/percona-server/5.5/installation/apt_repo.html
* http://www.percona.com/doc/percona-server/5.5/performance/handlersocket.html
* https://github.com/DeNADev/HandlerSocket-Plugin-for-MySQL/blob/master/docs-en/configuration-options.en.txt
* http://dev.mysql.com/tech-resources/articles/mysql_i_s_plugins_part1-2.html
