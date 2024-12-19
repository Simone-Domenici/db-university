## JOIN

### 1. Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia
```sql
SELECT `students`.*, `degrees`.`name` AS `degree_name`
FROM `students`
JOIN `degrees` ON `students`.`degree_id` = `degrees`.`id`
WHERE `degrees`.`name` = 'Corso di Laurea in Economia';
```
### 2. Selezionare tutti i Corsi di Laurea Magistrale del Dipartimento di Neuroscienze
```sql
SELECT `degrees`.*, `departments`.`name` AS `department_name`
FROM `departments`
JOIN `degrees` ON `degrees`.`department_id` = `departments`.`id`
WHERE `departments`.`name` = 'Dipartimento di Neuroscienze'
AND `degrees`.`level` = 'magistrale';
```
### 3. Selezionare tutti i corsi in cui insegna Fulvio Amato (id=44)
```sql
SELECT `courses`.`name`, `teachers`.`id`, `teachers`.`name` AS `teacher_name`, `teachers`.`surname` AS `teacher_surname`
FROM `teachers`
JOIN `course_teacher` ON `course_teacher`.`teacher_id` = `teachers`.`id`
JOIN `courses` ON `course_teacher`.`course_id` = `courses`.`id`
WHERE `teachers`.`id` = 44;
```
### 4. Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui sono iscritti e il relativo dipartimento, in ordine alfabetico per cognome e nome
```sql
SELECT `students`.*, `departments`.`name` AS `department_name`, `degrees`.`name` AS `degree_name`
FROM `students`
JOIN `degrees` ON `students`.`degree_id` = `degrees`.`id`
JOIN `departments` ON `degrees`.`department_id` = `departments`.`id`
ORDER BY `students`.`surname`, `students`.`name` ASC;
```