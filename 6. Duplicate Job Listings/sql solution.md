```sql
WITH cte
AS
(
SELECT 
  company_id,
  title,
  COUNT(company_id) AS count_
FROM job_listings
GROUP BY title, company_id
)

SELECT 
  COUNT(DISTINCT title) AS duplicate_companies
FROM cte
WHERE count_ > 1;
```
