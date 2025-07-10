1. `Contare quanti iscritti ci sono stati ogni anno`

1. SELECT enrolment_date, COUNT(*) AS registration_number
FROM students
GROUP BY enrolment_date;

2. `Contare gli insegnanti che hanno l'ufficio nello stesso edificio`

2. SELECT office_address, COUNT(*) AS teachers_number
FROM teachers
GROUP BY office_address;

3. `Calcolare la media dei voti di ogni appello d'esame`

3. SELECT exam_id, AVG(vote) AS media_voti
FROM exam_student
GROUP BY exam_id;

4. `Contare quanti corsi di laurea ci sono per ogni dipartimento`

4. SELECT department_id, COUNT(*) AS numero_corsi
FROM degrees
GROUP BY department_id;



- JOIN 

1. `Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia`

1. SELECT students.*
FROM students
JOIN degrees ON students.degree_id = degrees.id
WHERE degrees.name LIKE '%Economia%';


2. `Selezionare tutti i Corsi di Laurea Magistrale del Dipartimento di Neuroscienze`

2. SELECT degree.*
FROM degree
JOIN departments ON degree.department_id = departments.id
WHERE degree.level = 'Magistrale'
  AND departments.name = 'Neuroscienze';



3. ` Selezionare tutti i corsi in cui insegna Fulvio Amato (id=44)`


3.  SELECT courses.*
FROM courses
JOIN course_teacher ON courses.id = course_teacher.course_id
WHERE course_teacher.teacher_id = 44;


4. `Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui sono iscritti e il relativo dipartimento, in ordine alfabetico per cognome e nome `

4. SELECT students.name, students.surname, degrees.name AS degree_name, departments.name AS department_name
FROM students
JOIN degrees ON students.degree_id = degrees.id
JOIN departments ON degrees.department_id = departments.id
ORDER BY students.surname ASC, students.name ASC;



5. 

5. 


6. 


7. 


6. 


7. 