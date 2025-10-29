📚 LibraryX – Interactive Library Management System

License: MIT  Tech Stack: Java • Swing • MySQL • IntelliJ IDEA

🎯 Overview

LibraryX is an interactive desktop application designed to simplify and digitalize library operations.
Built with Java Swing for a user-friendly GUI and MySQL for reliable data management, it allows librarians and students to manage books, students, and borrowing records efficiently.

🧩 Core Modules

Book Management – Add, update, search, and delete books

Student Management – Register and maintain student records

Issue/Return System – Track which student has borrowed which book

Database Integration – Persistent MySQL backend for data storage

GUI Forms – Built using Swing Form Designer (.form files)

✨ Features
📘 Library Operations

Add new books with title, author, and ISBN

Edit or delete book records dynamically

Maintain student details (Name, Roll No., etc.)

Issue and return books using easy-to-use mapping interface

🎨 User Interface

Form-based GUI: Built with Java Swing and IntelliJ Form Designer

Intuitive Layout: Clear menus and dialog boxes for all operations

Responsive Controls: Buttons, text fields, and labels integrated seamlessly

🧠 Database Layer

Uses JDBC for database connectivity

Database.java handles all MySQL queries and connections

Configurable credentials for flexible setup

⚙️ Technical Architecture

Core Technologies:

Language: Java (JDK 8 or above)

GUI Library: Swing

Database: MySQL

IDE: IntelliJ IDEA

Key Classes and Forms:

File	Description
LibraryGUI.java	Main interface for managing library operations
BookRegistrationForm.java	GUI form for adding and editing book details
StudentBookMappingGUI.java	GUI for mapping students to borrowed books
Database.java	Handles all MySQL database operations
College/Book.java	Data model for a single book
College/Student.java	Data model for a student
College/Library.java	Core logic for managing books and students
🧩 File Structure
LibraryX/
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
├── .idea/
├── practice.java.iml
└── README.md

🚀 Getting Started
🧱 Prerequisites

JDK 8+

MySQL Server

IntelliJ IDEA or Eclipse

🧩 Setup Steps

Clone or extract the repository:

unzip LibraryX.zip
cd LibraryX


Open the project in IntelliJ IDEA.

Create MySQL Database:

CREATE DATABASE library_db;


Configure connection in Database.java:

Connection con = DriverManager.getConnection(
    "jdbc:mysql://localhost:3306/library_db", "username", "password");


Run the application:
Execute LibraryGUI.java from IntelliJ or command line.

🧠 Database Schema (Example)
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

🎮 Usage Guide
📗 Adding a Book

Open Book Registration Form

Enter title, author, ISBN

Click Save

🧑‍🎓 Registering a Student

Open Student Management form

Enter student name and roll number

Click Register

🔁 Issuing a Book

Open Student-Book Mapping

Select student and book

Click Issue Book

🔄 Returning a Book

Select issued record

Click Return Book

🎨 Design & UX Highlights

Clean, form-based layout with organized input fields

Visual feedback for successful/failed actions

Simple and accessible for beginners and admins alike

🧠 Educational Value

Demonstrates Object-Oriented Programming (OOP) in Java

Integrates GUI Programming with Swing

Implements JDBC Database Handling

Practical example of Model–View–Controller (MVC) design

🔧 Customization

You can easily modify:

Database credentials in Database.java

Table schema for additional attributes

GUI layouts via IntelliJ’s Form Designer

🤝 Contributing

We welcome contributions!

Steps:

Fork the repo

Create a branch: git checkout -b feature-name

Make your changes

Commit and push:

git add .
git commit -m "Add new feature"
git push origin feature-name


Submit a Pull Request

🧭 Roadmap

v2.0 (Planned):

Add book search and filtering

Generate PDF issue reports

Add login and role-based access

v2.1 (Future):

Cloud-based MySQL support

Enhanced analytics dashboard

Integration with barcode scanning

🧾 License

This project is licensed under the MIT License — see the LICENSE file for details.

🙏 Acknowledgments

Java Swing Developers Community for GUI framework

MySQL Team for open-source database tools

IntelliJ IDEA for robust Java development environment

Built with ❤️ for education and library management efficiency
