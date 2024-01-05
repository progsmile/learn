
Create DB
```sql
CREATE DATABASE IF NOT EXISTS 'my_awesome_db' CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
```

Get DB version
```sql
SELECT VERSION();
```

Show table structure
```mysql
DESCRIBE users;
SHOW FULL COLUMNS FROM users;
```

Get table information (Engine, Row_format, Collation)
```sql
SHOW TABLE STATUS LIKE 'users'
```

Show table indexes
```sql
SHOW INDEX FROM users;
```

---
Grants
```sql
SHOW GRANTS FOR 'mysql'@'localhost'
```

```sql
GRANT ALL PRIVILEGES ON `DB_NAME`.* TO `user`@`localhost`;

GRANT SELECT (id, title, description), UPDATE (description) ON `DB_NAME`.`books` TO `my_awesome_user`@`%`
```

---
Dump
```bash
# Export data
mysqldump -u db_user -p db_name table1 table2 --where="created_at > '2017-12-31 11:12:13'" --no-create-info --replace --skip-triggers > dump.sql 

# Import data
mysql -u db_user -p --default-character-set=utf8 db_name < ./dump.sql
```

