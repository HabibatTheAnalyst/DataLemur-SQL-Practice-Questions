```sql
SELECT
  sender_id,
  COUNT(sender_id) AS message_count
FROM messages
WHERE sent_date BETWEEN '08-01-2022' AND '08-31-2022'
GROUP BY sender_id
ORDER BY message_count DESC
LIMIT 2
```
