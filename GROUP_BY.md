## GROUP BY

### 1. Contare quanti iscritti ci sono stati ogni anno
```sql
SELECT COUNT(id) AS `students_subscription`, YEAR(`enrolment_date`) AS `year`
FROM `students`
GROUP BY YEAR(`enrolment_date`);
```