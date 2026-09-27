---
tags:
  - insy
  - 5te_klasse
created: 2026-09-23T10:26:24+02:00
modified: 2026-09-23T10:30:18+02:00
---
```sql
CREATE TABLE students (
student_id INT PRIMARY KEY,
first_name VARCHAR(50) NOT NULL,
last_name VARCHAR(50) NOT NULL,
date_of_birth DATE,
email VARCHAR(100) UNIQUE,
fk_course_id INT,
FOREIGN KEY (fk_course_id) REFERENCES courses(course_id)
ON DELETE SET NULL
ON UPDATE CASCADE
);
  
CREATE TABLE courses (
course_id INT PRIMARY KEY,
course_name VARCHAR(100) NOT NULL
);
  
INSERT INTO courses (course_id, course_name) VALUES
(1, 'Mathematics'),
(2, 'Physics'),
(3, 'Chemistry'),
(4, 'Biology'),
(5, 'Computer Science');

INSERT INTO students (student_id, first_name, last_name, date_of_birth, email, fk_course_id) VALUES
(1, 'John', 'Doe', '2000-01-15', 'john.doe@example.com', 1),
(2, 'Jane', 'Smith', '1999-05-22', 'jane.smith@example.com', 2),
(3, 'Alice', 'Johnson', '2001-03-10', 'alice.johnson@example.com', 3),
(4, 'Bob', 'Brown', '2000-07-30', 'bob.brown@example.com', 4),
(5, 'Charlie', 'Davis', '1998-11-12', 'charlie.davis@example.com', 5),
(6, 'Emily', 'Wilson', '2001-09-05', 'emily.wilson@example.com', 5),
(7, 'David', 'Miller', '1999-12-20', 'david.miller@example.com', 1),
(8, 'Sophia', 'Taylor', '2000-04-18', 'sophia.taylor@example.com', 2),
(9, 'Liam', 'Anderson', '2002-02-14', 'liam.anderson@example.com', 3),
(10, 'Olivia', 'Thomas', '2001-06-27', 'olivia.thomas@example.com', 1),
(11, 'Noah', 'Jackson', '1999-08-09', 'noah.jackson@example.com', 5),
(12, 'Emma', 'White', '2000-10-03', 'emma.white@example.com', 2),
(13, 'Lucas', 'Harris', '2002-01-19', 'lucas.harris@example.com', 4),
(14, 'Mia', 'Martin', '2001-07-11', 'mia.martin@example.com', 3),
(15, 'James', 'Thompson', '1998-04-25', 'james.thompson@example.com', 5),
(16, 'Ava', 'Garcia', '2000-12-17', 'ava.garcia@example.com', 1),
(17, 'Benjamin', 'Clark', '2001-11-28', 'benjamin.clark@example.com', 2),
(18, 'Isabella', 'Lewis', '1999-03-30', 'isabella.lewis@example.com', 4),
(19, 'Henry', 'Walker', '2002-05-06', 'henry.walker@example.com', 5),
(20, 'Charlotte', 'Hall', '2001-09-23', 'charlotte.hall@example.com', 3),
(21, 'Alexander', 'Allen', '2000-08-16', 'alexander.allen@example.com',1),
(22, 'Ella', 'Young', '2002-10-08', 'ella.young@example.com', 2),
(23, 'Daniel', 'King', '1999-01-21', 'daniel.king@example.com', 4),
(24, 'Grace', 'Wright', '2001-04-14', 'grace.wright@example.com', 5),
(25, 'Michael', 'Scott', '2000-06-02', 'michael.scott@example.com', 3),
(26, 'Harper', 'Green', '2002-03-12', 'harper.green@example.com', 1),
(27, 'Samuel', 'Baker', '1998-07-18', 'samuel.baker@example.com', 2),
(28, 'Amelia', 'Adams', '2001-12-05', 'amelia.adams@example.com', 4);
```