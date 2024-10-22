
### DB & table information

Create DB
```sql
CREATE DATABASE IF NOT EXISTS 'my_awesome_db' CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
```

Get DB version, encoding
```sql
SELECT VERSION();

SELECT @@character_set_database, @@collation_database;
```

Show table structure
```mysql
SHOW CREATE TABLE users;
DESC users;
DESCRIBE users;
SHOW FULL COLUMNS FROM users;
```

Get table information (Engine, Row_format, Collation)
```sql
SHOW TABLE STATUS LIKE 'users';
```

Show table indexes
```sql
SHOW INDEX FROM users;
```

Show all db triggers
```sql
SELECT * FROM information_schema.TRIGGERS WHERE TRIGGER_SCHEMA = DATABASE();
```

Create table from query
```sql
CREATE TABLE users_debug AS SELECT * FROM users WHERE is_active = true;
```

Get running processes
```sql
SHOW FULL PROCESSLIST;
```

Kill process by id
```sql
KILL {id};
```


### Users & Grants

Users
```sql
SELECT user FROM mysql.user;
```

Grants
```sql
SHOW GRANTS FOR 'mysql'@'localhost';
```

```sql
GRANT ALL PRIVILEGES ON `DB_NAME`.* TO `user`@`localhost`;

GRANT SELECT (id, title, description), UPDATE (description) ON `DB_NAME`.`books` TO `my_awesome_user`@`%`;
```

Set password
```sql
SET PASSWORD FOR `john`@`%` = 'p@$$w0rd';
```

### mysqldump

```bash
# Export data. Closely pay attention when using `--replace`, so table records matches correctly by primary key. 
mysqldump -u db_user -p db_name table1 table2 --where="created_at > '2017-12-31 11:12:13'" --no-create-info --replace --skip-triggers --complete-insert > dump.sql 

# Import data
mysql -u db_user -p --default-character-set=utf8 db_name < ./dump.sql
```

### Transactions
```sql
START TRANSACTION;
-- Do some sql;
COMMIT; -- or ROLLBACK;
```

### Profiling

Check status
```sql
SHOW VARIABLES LIKE 'profiling';
SET profiling = 1; -- or 0
```

Measure sql query
```sql
-- Do sql query
SHOW PROFILES;
```
