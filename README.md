📘 Library Management System (Java GUI Project)
🧾 Overview

This Java project is a Library Management System built using Swing GUI and JDBC for database connectivity.
It allows users to manage books, students, and their book issue/return records efficiently through a simple graphical interface.

🗂️ Project Structure
practice.java/
├── src/
│   ├── College/
│   │   ├── Book.java
│   │   ├── Books.java
│   │   ├── Library.java
│   │   ├── Student.java
│   │   └── Students.java
│   ├── BookRegistrationForm.java
│   ├── LibraryGUI.java
│   ├── StudentBookMappingGUI.java
│   └── Database.java
├── .idea/               # IntelliJ project settings
├── practice.java.iml    # IntelliJ module file
└── .gitignore

🧠 Features

Book Management: Add, update, or remove books in the library.

Student Management: Register students with unique IDs.

Book Issue & Return: Map books to students and manage borrowing records.

Database Integration: Uses MySQL for persistent storage.

Graphical Interface: Built using Java Swing and Form Designer (.form files).

⚙️ Technologies Used

Language: Java (JDK 8+)

GUI Library: Swing

Database: MySQL

IDE: IntelliJ IDEA (recommended)

Connector: MySQL JDBC Driver (mysql_connector_j_9_1_0.xml)

🧩 How to Run

Clone or extract the project:

unzip e01c9711-893b-46d7-ad28-83722dc3e1a4.zip


Open the project in IntelliJ IDEA.

Configure the database:

Create a MySQL database (e.g., library_db).

Update credentials in Database.java:

Connection con = DriverManager.getConnection(
    "jdbc:mysql://localhost:3306/library_db", "username", "password");


Run the application:

Execute LibraryGUI.java to start the main interface.

🧑‍💻 Key Classes
File	Description
LibraryGUI.java	Main GUI interface for managing library operations.
BookRegistrationForm.java	Handles book registration.
StudentBookMappingGUI.java	Maps students to borrowed books.
Database.java	Manages MySQL database connections and queries.
College/Book.java	Represents a single book entity.
College/Student.java	Represents a single student entity.
💾 Database Schema (Suggested)
CREATE TABLE books (
    id INT AUTO_INCREMENT PRIMARY KEY,
    title VARCHAR(100),
    author VARCHAR(100),
    isbn VARCHAR(50),
    available BOOLEAN DEFAULT TRUE
);

CREATE TABLE students (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100),
    roll_no VARCHAR(50) UNIQUE
);

CREATE TABLE book_issue (
    id INT AUTO_INCREMENT PRIMARY KEY,
    student_id INT,
    book_id INT,
    issue_date DATE,
    return_date DATE,
    FOREIGN KEY (student_id) REFERENCES students(id),
    FOREIGN KEY (book_id) REFERENCES books(id)
);

🧩 Future Enhancements

Add search functionality for books and students.

Include book return reminders.

Implement report generation (PDF/Excel).

Improve UI design with JavaFX or modern frameworks.

📜 License

This project is free for educational use and modification.
