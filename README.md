# Esercizi con SELECT

### 1. Selezionare tutti gli studenti nati nel 1990
```sql
SELECT *
FROM `students`
WHERE YEAR(date_of_birth) = 1990;
```
### 2. Selezionare tutti i corsi che valgono più di 10 crediti
```sql
SELECT * 
FROM `courses` 
WHERE cfu > 10;
```
### 3. Selezionare tutti gli studenti che hanno più di 30 anni
```sql
SELECT * 
FROM `students` 
WHERE TIMESTAMPDIFF(YEAR, date_of_birth, CURDATE()) > 30;
```
### 4. Selezionare tutti i corsi del primo semestre del primo anno di un qualsiasi corso di laurea
```sql
SELECT * 
FROM `courses` 
WHERE period = 'I semestre'  AND year = 1;
```
### 5. Selezionare tutti gli appelli d'esame che avvengono nel pomeriggio (dopo le 14) del 20/06/2020
```sql
SELECT * 
FROM `exams`
WHERE `date` = '2020-06-20' AND `hour` > '14:00:00';
```
### 6. Selezionare tutti i corsi di laurea magistrale
```sql
SELECT * 
FROM `degrees` 
WHERE level = 'magistrale';
```
### 7. Da quanti dipartimenti è composta l'università?
```sql
SELECT COUNT(*) 
AS `total_departments` 
FROM `departments`;
```
### 8. Quanti sono gli insegnanti che non hanno un numero di telefono?
```sql
SELECT COUNT(*) 
AS `teachers_without_phone` 
FROM `teachers` 
WHERE phone IS NULL;
```
### 9. Inserire nella tabella degli studenti un nuovo record con i propri dati
```sql
INSERT INTO `students`(name, surname, date_of_birth, fiscal_code, enrolment_date, registration_number , email, degree_id) 
VALUE ('Simone', 'Domenici', '2000-04-11', 'DMNSMN00D11H501N', CURDATE(), '690096', 'simone00@gmail.com', '69');
```
### 10. Cambiare il numero dell'ufficio del professor Pietro Rizzo in 126
```sql
UPDATE `teachers` 
SET office_number = 126 
WHERE name = 'Pietro' AND surname = 'Rizzo';
```
### 11. Eliminare dalla tabella studenti il record creato precedentemente al punto 9
```sql
DELETE 
FROM `students`
WHERE name = 'Simone' AND surname = 'Domenici' AND date_of_birth = '2000-04-11'
```

