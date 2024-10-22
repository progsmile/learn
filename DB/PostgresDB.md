## Connect
- `psql --username=my_user --host=localhost --port=5432 --password --dbname=my_db`

## Change connection
- `\c my_2nd_db` or `\connect my_2nd_db`

## List databases
- `\l` or `\list`

## Create dump
- `pg_dump --username=my_user --host=localhost --port=5432 --password --dbname=my_db > dump.sql`

## Import SQL
- `psql --username=my_user --host=localhost --port=5432 --password --dbname=my_db < dump.sql`


---
## JSON like query  

```sql
SELECT * FROM module_data WHERE data::json->>'title' ilike '%Board%'
```


