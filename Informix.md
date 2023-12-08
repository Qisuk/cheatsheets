
# Informix

## list all tables and columns in DB
```sql
SELECT TRIM(t.tabname) || '.' || TRIM(c.colname) AS table_dot_column
  FROM "informix".systables  AS t
  JOIN "informix".syscolumns AS c ON t.tabid = c.tabid
 WHERE t.tabtype = 'T'
   AND t.tabid >= 100
 ORDER BY t.tabname, c.colno;
 ```
 Jonathan Leffler
https://stackoverflow.com/questions/1380782/informix-sql-list-all-fields-tables