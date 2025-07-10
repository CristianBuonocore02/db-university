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


2. 

2. 


3. 


3.  

4. 

4. 


5. 

5. 


6. 


7. 


6. 


7. 