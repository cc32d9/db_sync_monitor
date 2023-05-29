# db_sync_monitor

These are health check scripts for Nagios or Icinga, verifying the
"block_time" column in SYNC table in the specified database.

The scripts connect to a Postgres or MySQL database, respectively, and
compare `MIN(block_time)` with current time. They return a Warning or
Critical status if the time in the database is too far from current
time.


```
apt install -y git libdatetime-format-iso8601-perl libdbi-perl libdbd-pg-perl libdbd-mysql-perl libdatetime-format-pg-perl libdatetime-format-mysql-perl libjson-xs-perl libjson-perl

git clone https://github.com/cc32d9/db_sync_monitor.git /opt/db_sync_monitor


/opt/db_sync_monitor/check_db_sync_mysql --database=memento_eos --dbhost=memento.eu.eosamsterdam.net --dbport=3350 --dbuser=memento_ro --dbpw=memento_ro 

/opt/db_sync_monitor/check_db_sync_pg --database=tblstate_eos --dbhost=10.0.3.60 --dbuser=tblstate_ro --dbpw=tblstate_ro

```
