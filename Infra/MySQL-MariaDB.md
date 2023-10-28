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
