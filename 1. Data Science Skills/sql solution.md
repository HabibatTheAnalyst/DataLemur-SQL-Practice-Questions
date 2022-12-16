```sql
WITH cte_ 
as 
(
SELECT candidate_id,
COUNT(skill) as skills
FROM candidates
Where skill IN ('Python', 'Tableau', 'PostgreSQL')
GROUP BY candidate_id
)

SELECT candidate_id
FROM cte_
WHERE skills = 3
ORDER BY candidate_id;
```
