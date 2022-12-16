```sql
SELECT city,
  SUM(CASE WHEN status = 'Completed' THEN 1
           WHEN status = 'Cancelled' THEN 1 ELSE 0 END) AS total_orders
FROM trades AS t
FULL OUTER JOIN users AS u
ON t.user_id = u.user_id
WHERE status = 'Completed'
GROUP BY city
ORDER BY total_orders DESC
LIMIT 3;
```
