## GROUP BY

### 1. Contare quanti iscritti ci sono stati ogni anno
```sql
SELECT COUNT(id) AS `students_subscription`, YEAR(`enrolment_date`) AS `year`
FROM `students`
GROUP BY YEAR(`enrolment_date`);
```
### 2. Contare gli insegnanti che hanno l'ufficio nello stesso edificio
```sql
SELECT COUNT(id) AS `teachers`, `office_address`
FROM `teachers`
GROUP BY `office_address`;
```
