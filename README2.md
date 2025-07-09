1. Contare quanti iscritti ci sono stati ogni anno

1. SELECT enrolment_date, COUNT(*) AS registration_number
FROM students
GROUP BY enrolment_date;

2. Contare gli insegnanti che hanno l'ufficio nello stesso edificio

2. SELECT office_address, COUNT(*) AS teachers_number
FROM teachers
GROUP BY office_address;