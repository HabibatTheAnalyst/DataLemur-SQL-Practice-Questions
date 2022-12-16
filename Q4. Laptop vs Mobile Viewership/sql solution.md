```sql
WITH cte
AS
(
SELECT *,
    CASE WHEN device_type IN ('tablet', 'phone') THEN 1 ELSE 0 END AS mobile,
    CASE WHEN device_type = 'laptop' THEN 1 ELSE 0 END AS laptop
FROM viewership
)

SELECT
  SUM(mobile) AS mobile_views,
  SUM(laptop) AS laptop_views
FROM cte;
```
