# Question 4

Create a SQL query that returns the username, full name (Last Name, First Name) and last login date and time based on the following tables.
- The fields returned should be labeled username, full_name, last_login
- Each user should appear once in the result set
- Remember to include the user who has never logged in.
- The SQL below is designed and tested using MySQL.
- Save your answer in a file named logins.sql
- Add and commit your file
- This question is open book/open internet


`CREATE TABLE users (
	username VARCHAR(32) NOT NULL,
	password VARCHAR(32) NOT NULL,
	first_name VARCHAR(255) NOT NULL,
	last_name VARCHAR(255),
	PRIMARY KEY (`username`));

	CREATE TABLE logins (
	username VARCHAR(32) NOT NULL,
	last_login TIMESTAMP,
	FOREIGN KEY (`username`) REFERENCES users(`username`));

	INSERT INTO users
	VALUES
	('bob','9f9d51bc70ef21ca5c14f307980a29d8','Bob','Smith'),
	('joe','8ff32489f92f33416694be8fdc2d4c22','Joe','Smith'),
	('jane','5844a15e76563fedd11840fd6f40ea7b','Jane','Smith'),
	('matt','ce86d7d02a229acfaca4b63f01a1171b','Matt','Smith');

	INSERT INTO logins
	VALUES
	('bob','2011-01-02 06:42:15'),
	('bob','2011-01-12 13:42:15'),
	('jane','2011-01-02 08:42:15'),
	('matt','2011-01-13 09:42:15'),
	('jane','2011-01-14 12:42:15');``
