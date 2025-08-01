# db-university

Modellizzare la struttura di un database per memorizzare tutti i dati riguardanti una università:
sono presenti diversi ``Dipartimenti`` (es.: Lettere e Filosofia, Matematica, Ingegneria ecc.);
ogni Dipartimento offre più Corsi di Laurea (es.: Civiltà e Letterature Classiche, Informatica, Ingegneria Elettronica ecc..)
ogni Corso di Laurea prevede diversi Corsi (es.: Letteratura Latina, Sistemi Operativi 1, Analisi Matematica 2 ecc.);
ogni Corso può essere tenuto da diversi Insegnanti;
ogni Corso prevede più appelli d'Esame;
ogni Studente è iscritto ad un solo Corso di Laurea;
ogni Studente può iscriversi a più appelli di Esame;
per ogni appello d'Esame a cui lo Studente ha partecipato, è necessario memorizzare il voto ottenuto, anche se non sufficiente. Pensiamo a quali entità (tabelle) creare per il nostro database e cerchiamo poi di stabilirne le relazioni. Infine, andiamo a definire le colonne e i tipi di dato di ogni tabella.



## Departement  
- id
- degree-courses_id
- sector 
- addresses 

## degree-courses
- id
- payment
- faculty
- academic-year

## course
- id 
- degree-courses_id
- name-course
- class
- total-hours

## students
- id 
- degree-courses_id 
- name 
- lastName 
- gender
- age 
- average 

## teachers  
- id 
- degree-courses_id
- matter 
- name
- age 
- experience 

## exams
- id
- duration
- difficulty  



1. Selezionare tutti gli studenti nati nel 1990 (160)    


1. SELECT * FROM university_db.students
WHERE year(date_of_birth) = 1990;



2. Selezionare tutti i corsi che valgono più di 10 crediti (479)


2. SELECT * FROM university_db.courses
WHERE cfu > 10 ;


3. Selezionare tutti gli studenti che hanno più di 30 anni


3. SELECT * FROM university_db.students
WHERE TIMESTAMPDIFF(YEAR, date_of_birth, CURDATE()) > 30;


4. Selezionare tutti i corsi del primo semestre del primo anno di un qualsiasi corso di
laurea (286)

4. SELECT * FROM university_db.courses
WHERE year = 1 AND period = 1;

5. Selezionare tutti gli appelli d'esame che avvengono nel pomeriggio (dopo le 14) del
20/06/2020 (21)

5. SELECT * FROM university_db.exams
WHERE date = '2020-06-20' AND HOUR(hour) > 14;

6. Selezionare tutti i corsi di laurea magistrale (38)

6. SELECT * FROM university_db.degrees
WHERE level = 'magistrale';

7. Da quanti dipartimenti è composta l'università? (12)

8. Quanti sono gli insegnanti che non hanno un numero di telefono? (50)

8. SELECT * FROM university_db.teachers
WHERE PHONE IS NULL OR PHONE = '';