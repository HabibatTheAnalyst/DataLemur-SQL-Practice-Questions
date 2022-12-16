```sql
SELECT
p.page_id
FROM pages as p
LEFT JOIN page_likes as pl
ON p.page_id = pl.page_id
WHERE liked_date IS NULL
ORDER BY page_id ASC;
```
