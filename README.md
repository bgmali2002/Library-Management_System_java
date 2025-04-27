# Library Management System

This is a Library Management System built using **Java Swing** for the graphical user interface (GUI) and **MariaDB** for the database. The system allows administrators to manage books, students, issue and return books, and generate reports.

## Features
- **Login Panel**: Secure authentication for administrators.
- **Add Book**: Add new books to the library.
- **Add Student**: Register new students to the system.
- **Issue Book**: Issue books to students.
- **Return Book**: Handle book returns and calculate fines.
- **Report**: Generate a report of issued books, available books, and students.
- **Database Integration**: Data is stored and managed using MariaDB.

## Project Structure

LibraryManagementSystem/
│
├── src/
│   └── org.library_management/
│       ├── DBConnection.java
│       ├── LibraryApp.java
│       ├── panels/
│       │   ├── AddBookPanel.java
│       │   ├── AddStudentPanel.java
│       │   ├── IssuePanel.java
│       │   ├── ReturnPanel.java
│       │   ├── ReportPanel.java
│       │   └── LoginPanel.java
│       ├── models/
│       │   ├── Book.java
│       │   ├── Student.java
│       │   └── IssuedBook.java
-       -

  
## Prerequisites

To run this project, you need the following:

- **Java**: Version 8 or higher
- **MariaDB**: A local or remote MariaDB instance
- **IntelliJ IDE** or any IDE that supports Java development

## Setup
Setup MariaDB:

Install MariaDB on your local machine or set up a remote server.

Create the *"library_db"* database and run the provided SQL script to set up the required tables.

CREATE DATABASE library_db;

USE library_db;

CREATE TABLE books (
    id INT AUTO_INCREMENT PRIMARY KEY,
    title VARCHAR(255),
    author VARCHAR(255),
    publisher VARCHAR(255),
    available BOOLEAN
);

CREATE TABLE students (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(255),
    email VARCHAR(255)
);

CREATE TABLE issued_books (
    id INT AUTO_INCREMENT PRIMARY KEY,
    book_id INT,
    student_id INT,
    issue_date DATE,
    return_date DATE,
    FOREIGN KEY (book_id) REFERENCES books(id),
    FOREIGN KEY (student_id) REFERENCES students(id)
);


Configure Database Connection:

Edit the DBConnection.java file to provide your MariaDB connection details (URL, username, password).

Run the Application:

Open the project in your IDE (e.g., NetBeans).

Run the LibraryApp.java file to start the application.

-------------------------------------------------------------------------------
🙌 Author
BHERUNATH GEHLOT
📧 Email: bhanwarm99@gmail.com
🔗 LinkedIn: linkedin.com/in/yourprofile
💻 GitHub: github.com/bgmali2002
