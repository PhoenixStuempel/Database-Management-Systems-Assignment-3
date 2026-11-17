# COMP 3005 Assignment 3

This is a Python program that establishes a connection to a PostgreSQL database and performs CRUD operations on the students table. The schema.sql file creates the students table and inserts some starting data into that table, while the students_crud.py file contains the program which performs the four specified functions. The requirements.txt file lists psycopg, the PostgreSQL driver the program needs to run.

Demo video: https://youtu.be/2F3sJDaht5s

## Setup

Yopu will need Python 3, PostgreSQL, and pgAdmin. The Windows PostgreSQL installer can be downloaded at https://www.postgresql.org/download/windows/ and provides pgAdmin. 

In pgAdmin, create a database called school by right-clicking Databases > Create > Database... Then choose the school database, launch the Query Tool, open the schema.sql file and run it with the play button (or F5). This will create the table and insert the three initial student records.

Install the Python PostgreSQL driver with pip install -r requirements.txt. If the PostgreSQL username and/or password are anything other than the default postgres, change them in the connect() function in students_crud.py.

## Running the program

The program can be run directly inside the shell/typed into a terminal. Call each function using the command for it:

```
python students_crud.py list
python students_crud.py add Marty McFly outatime@example.com 2015-10-21
python students_crud.py update-email 2 mrs.smith@example.com
python students_crud.py delete 3
```

- getAllStudents() (the list command): lists all the student records within the table.
- addStudent(first_name, last_name, email, enrollment_date) (the add command): adds a new student record
  with all the details of the new student.
- updateStudentEmail(student_id, new_email) (the update-email command): updates the email address of the
  specified student.
- deleteStudent(student_id) (the delete command): deletes the student record.

To check that the changes have been made, go to the school database in pgAdmin and browse
Schemas > public > Tables > students, then right-click and choose View/Edit Data > All Rows.
Press F5 after each command to view the results.
