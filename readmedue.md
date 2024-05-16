PRIMO FILE

1. Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia

SELECT * FROM `students` INNER JOIN `degrees` ON `students`.`degree_id` = `degrees`.`id` WHERE `degrees`.`name` = 'Corso di Laurea in Economia';

2. Selezionare tutti i Corsi di Laurea Magistrale del Dipartimento di Neuroscienze

SELECT * FROM `degrees` INNER JOIN `departments` ON `departments`.`id` = `degrees`.`department_id` WHERE `departments`.`name` = 'Dipartimento di Neuroscienze' AND `degrees`.`name`LIKE '%Magistrale%';

3. Selezionare tutti i corsi in cui insegna Fulvio Amato (id=44)

SELECT * FROM `teachers` INNER JOIN `course_teacher` ON `teachers`.`id` = `course_teacher`.`teacher_id` WHERE `teachers`.`id` = 44;

4. Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui sono iscritti e il relativo dipartimento, in ordine alfabetico per cognome e nome

SELECT * FROM `students` INNER JOIN `degrees` ON `degrees`.`id` = `students`.`degree_id` INNER JOIN `departments` ON `departments`.`id` = `degrees`.`department_id` ORDER BY `students`.`name`, `students`.`surname` ASC;

5. Selezionare tutti i corsi di laurea con i relativi corsi e insegnanti

SELECT
    `degrees`.`name`,
    `courses`.`name`,
    `courses`.`period`,
    `courses`.`year`,
    `courses`.`cfu`,
    `teachers`.`name`,
    `teachers`.`surname`
FROM `degrees`
    INNER JOIN `courses` ON `degrees`.`id` = `courses`.`degree_id`
    INNER JOIN `course_teacher` ON `courses`.`id` = `course_teacher`.`course_id`
    INNER JOIN `teachers` ON `course_teacher`.`teacher_id` = `teachers`.`id`;

6. Selezionare tutti i docenti che insegnano nel Dipartimento di Matematica (54)




SECONDO FILE

1. Contare quanti iscritti ci sono stati ogni anno


2. Contare gli insegnanti che hanno l'ufficio nello stesso edificio


3. Calcolare la media dei voti di ogni appello d'esame


4. Contare quanti corsi di laurea ci sono per ogni dipartimento