
📚 Library Book Inventory Management System
A robust Java command-line application for managing a library's book inventory. The application provides a simple, interactive text-based interface for performing complete CRUD (Create, Read, Update, Delete) operations on books.

The system uses an in-memory data structure to store and manage book records, making it lightweight, easy to understand, and suitable for learning Java application architecture and service-layer design.

📖 Table of Contents
Overview
Features
Technology Stack
Project Structure
Book Information
Application Architecture
CRUD Operations
Input Validation
Prerequisites
Installation
Compilation and Execution
Using the Application
Searching Books
Updating Books
Deleting Books
Testing
Sample Workflow
Data Storage
Limitations
Possible Future Enhancements
Learning Objectives
Contributing
License
🔎 Overview
The Library Book Inventory Management System is a console-based Java application designed to simplify the management of books in a library.

Users can:

Add new books to the inventory
View all available books
Search for books using different attributes
Update information about an existing book
Delete books from the inventory
Validate user input before storing information
The project separates the book model, business logic, user interface, and testing logic into individual Java classes. This makes the application easier to maintain and provides a basic example of layered application design.

✨ Features
➕ Create — Add a Book
Users can add a new book by providing:

Book ID
Title
Author
ISBN
Publication Year
The application validates the provided information before adding the book to the inventory.

📖 Read — View and Search Books
Users can view all books currently stored in the inventory.

Books can also be searched using:

ID
Title
Author
ISBN
Publication Year
Search functionality makes it easier to locate a particular book without manually checking the entire inventory.

✏️ Update — Modify a Book
Existing book information can be modified.

Users can update details such as:

Title
Author
ISBN
Publication Year
The system first verifies that the requested book exists before applying changes.

🗑️ Delete — Remove a Book
Books can be removed from the inventory using their unique ID.

The application handles cases where the requested book does not exist and informs the user accordingly.

✅ Input Validation
The application performs basic validation to maintain reliable inventory data.

Examples include:

Preventing empty text fields
Validating numeric values
Ensuring publication years are realistic
Preventing publication years later than the current year
Handling invalid menu selections
Handling invalid book IDs
🛠️ Technology Stack
Technology	Purpose
Java	Application development
Java Collections	In-memory book storage
Java Scanner	Command-line input
JDK 8+	Java runtime and compiler
Standard Java APIs	Input validation and application logic
No external libraries or database systems are required.

📁 Project Structure
Library-Book-Inventory/
│
├── src/
│   ├── Book.java
│   ├── BookService.java
│   ├── Main.java
│   └── TestBookService.java
│
└── README.md
Book.java
Contains the Book model.

It represents an individual book and stores information such as:

ID
Title
Author
ISBN
Publication Year
The class is responsible for representing book data and typically contains constructors, getters, setters, and a toString() method.

BookService.java
Contains the application's business logic.

This class is responsible for managing the book inventory and implementing operations such as:

Adding books
Retrieving books
Searching books
Updating books
Deleting books
Keeping these operations in a separate service class prevents the user interface from becoming tightly coupled with the inventory logic.

Main.java
Acts as the application entry point.

It provides the command-line interface and interactive menu through which users can perform inventory operations.

The application continues running until the user chooses to exit.

TestBookService.java
Contains automated tests for the core functionality of BookService.

The test class can be used to verify that operations such as:

Create
Read
Search
Update
Delete
are working as expected.

📕 Book Information
Each book contains the following fields:

Field	Description	Example
ID	Unique identifier for the book	101
Title	Name of the book	Clean Code
Author	Book's author	Robert C. Martin
ISBN	International Standard Book Number	9780132350884
Publication Year	Year the book was published	2008
The ID is used to uniquely identify a book within the inventory.

🏗️ Application Architecture
The project follows a simple layered structure:

┌───────────────────────────┐
│          Main.java        │
│   Command-Line Interface  │
└─────────────┬─────────────┘
              │
              ▼
┌───────────────────────────┐
│      BookService.java     │
│    Business Logic / CRUD  │
└─────────────┬─────────────┘
              │
              ▼
┌───────────────────────────┐
│          Book.java        │
│        Data Model         │
└───────────────────────────┘
Flow of the application
User
  │
  ▼
Main.java
  │
  ▼
BookService
  │
  ├── Add
  ├── Search
  ├── List
  ├── Update
  └── Delete
  │
  ▼
Book Objects
  │
  ▼
In-Memory Collection
This separation provides a clear distinction between:

Presentation — command-line interface
Business logic — service layer
Data model — book entity
🔄 CRUD Operations
CRUD stands for:

Operation	Meaning	Application Function
Create	Add new data	Add Book
Read	Retrieve existing data	List/Search Books
Update	Modify existing data	Update Book
Delete	Remove existing data	Delete Book
Create
A new Book object is created and added to the inventory.

Enter Book ID: 101
Enter Title: Clean Code
Enter Author: Robert C. Martin
Enter ISBN: 9780132350884
Enter Publication Year: 2008
Read
The system can display all stored books or locate specific books based on search criteria.

Update
The application locates the book using its ID and modifies its stored information.

Delete
The application locates the book using its ID and removes it from the inventory.

🔐 Input Validation
Input validation helps prevent invalid data from entering the inventory.

Text Validation
Fields such as:

Title
Author
ISBN
should not be empty.

For example:

Enter Title:
Error: Title cannot be empty.
The user is prompted to enter the value again.

Publication Year Validation
The publication year must represent a realistic year.

For example, a future publication year should be rejected:

Enter Publication Year: 2035
Error: Publication year cannot be greater than the current year.
Numeric Validation
Numeric fields such as the book ID and publication year should contain valid numbers.

Invalid input should be rejected rather than causing the application to terminate unexpectedly.

📋 Prerequisites
Before running the application, make sure you have:

Java Development Kit (JDK) 8 or higher
A command-line terminal
Basic Java compilation support
To verify your Java installation:

java -version
You can also verify that the Java compiler is available:

javac -version
Example:

java version "17.x.x"
javac 17.x.x
The application does not require:

MySQL
PostgreSQL
MongoDB
Maven
Gradle
Any external Java libraries
🚀 Installation
1. Clone or download the project
If the project is hosted in a Git repository:

git clone <repository-url>
Navigate to the project directory:

cd Library-Book-Inventory
If you downloaded the project as a ZIP file, extract it and open a terminal inside the project directory.

▶️ Compilation and Execution
From the project root directory, compile all Java source files:

javac src/*.java
If compilation is successful, run the application:

java -cp src Main
The application will start and display the interactive menu.

🖥️ Using the Application
After starting the application, you will be presented with a menu similar to:

========================================
   LIBRARY BOOK INVENTORY MANAGEMENT
========================================

1. Add Book
2. List All Books
3. Search Book
4. Update Book
5. Delete Book
6. Exit

Enter your choice:
Select the required operation by entering its corresponding number.

➕ Adding a Book
Select:

1. Add Book
The application will request the book information.

Example:

Enter Book ID: 101
Enter Title: Clean Code
Enter Author: Robert C. Martin
Enter ISBN: 9780132350884
Enter Publication Year: 2008

Book added successfully!
The new book is then stored in the in-memory inventory.

📚 Listing All Books
Select:

2. List All Books
The application displays the books currently available.

Example:

ID: 101
Title: Clean Code
Author: Robert C. Martin
ISBN: 9780132350884
Publication Year: 2008
----------------------------------------
ID: 102
Title: Effective Java
Author: Joshua Bloch
ISBN: 9780134685991
Publication Year: 2018
----------------------------------------
If there are no books in the inventory, the application should display an appropriate message.

🔍 Searching Books
Select:

3. Search Book
The application can search using different fields, depending on the implementation.

Supported search criteria include:

Book ID
Title
Author
ISBN
Publication Year
For example:

Enter author: Robert C. Martin
The matching books are displayed.

Searching allows users to quickly find books without displaying or manually scanning the entire inventory.

✏️ Updating a Book
Select:

4. Update Book
The application first asks for the ID of the book to update.

Example:

Enter Book ID to update: 101

Enter new Title: Clean Code - Updated
Enter new Author: Robert C. Martin
Enter new ISBN: 9780132350884
Enter new Publication Year: 2008

Book updated successfully!
If the specified ID does not exist, the application reports that the book could not be found.

🗑️ Deleting a Book
Select:

5. Delete Book
Enter the ID of the book you want to remove:

Enter Book ID to delete: 101

Book deleted successfully!
Once deleted, the book will no longer appear in the inventory.

🚪 Exiting the Application
Select:

6. Exit
The application terminates gracefully.

Example:

Thank you for using the Library Book Inventory Management System.
Goodbye!
🧪 Testing
The project includes TestBookService.java for testing the core service-layer functionality.

Compile the source files:

javac src/*.java
Then execute the test class:

java -cp src TestBookService
The tests should verify the primary operations provided by BookService.

A typical test flow may include:

Creating a book...
✓ Book created successfully

Reading book...
✓ Book retrieved successfully

Searching book...
✓ Search successful

Updating book...
✓ Book updated successfully

Deleting book...
✓ Book deleted successfully
🔬 What Should Be Tested?
The service layer should ideally cover the following scenarios.

Create Tests
Successfully add a valid book
Prevent duplicate IDs, if uniqueness is enforced
Reject invalid book data
Read Tests
Retrieve an existing book
Handle a missing book
Retrieve all books
Search Tests
Search by ID
Search by title
Search by author
Search by ISBN
Search by publication year
Handle searches with no matching results
Update Tests
Update an existing book
Verify that updated values are stored
Attempt to update a nonexistent book
Delete Tests
Delete an existing book
Verify that it no longer exists
Attempt to delete a nonexistent book
🔄 Sample Workflow
A complete example workflow might look like this:

1. Start the application

2. Add a book
   ID: 1
   Title: The Pragmatic Programmer
   Author: Andrew Hunt
   ISBN: 9780135957059
   Year: 2019

3. Add another book
   ID: 2
   Title: Effective Java
   Author: Joshua Bloch
   ISBN: 9780134685991
   Year: 2018

4. List all books

5. Search for "Effective Java"

6. Update book ID 2

7. List all books again

8. Delete book ID 1

9. Verify the remaining inventory

10. Exit the application
💾 Data Storage
This application uses an in-memory data structure for storing books.

This means that book records exist only while the Java application is running.

For example:

Application Starts
       ↓
Books stored in memory
       ↓
CRUD operations
       ↓
Application exits
       ↓
Data is lost
Important
The application currently does not use persistent storage.

Restarting the application will clear the inventory unless the implementation is extended with a database or file-based storage mechanism.

⚡ Advantages of In-Memory Storage
Using an in-memory collection makes the project:

Simple to set up
Fast for basic operations
Easy to understand
Free from database configuration
Suitable for demonstrations and learning
Useful for testing service-layer logic
⚠️ Limitations
The current implementation is intentionally lightweight and has several limitations.

No Persistent Storage
All data is lost when the application terminates.

Command-Line Interface
The application is entirely text-based and does not provide a graphical or web interface.

Single-User Application
The system is designed for one user interacting with it through a terminal.

Limited Scalability
An in-memory collection is not appropriate for very large inventories or production environments requiring persistent, concurrent access.

Basic Authentication
The application does not currently provide user accounts, authentication, or role-based access control.

🚀 Possible Future Enhancements
The application can be extended in several ways.

💾 Database Integration
Add a relational database such as MySQL or PostgreSQL to persist book records.

Possible architecture:

Main
 ↓
BookService
 ↓
BookRepository
 ↓
Database
📄 File-Based Storage
Books could alternatively be stored in:

CSV
JSON
XML
Serialized Java objects
This would provide persistence without requiring a database server.

🌐 REST API
The service layer could be exposed through a REST API using a framework such as Spring Boot.

Possible endpoints:

GET    /books
GET    /books/{id}
POST   /books
PUT    /books/{id}
DELETE /books/{id}
🖥️ Graphical User Interface
A GUI could be developed using:

JavaFX
Swing
🔐 User Authentication
Add:

Librarian accounts
User accounts
Password authentication
Role-based permissions
📊 Advanced Search
Future versions could support:

Partial title matching
Case-insensitive searches
Multiple search criteria
Sorting by title
Sorting by author
Sorting by publication year
Pagination
📦 Inventory Enhancements
Additional book-related fields could include:

Genre
Publisher
Edition
Language
Number of copies
Availability status
Shelf location
Date added
🎯 Learning Objectives
This project is useful for practicing several fundamental Java concepts.

Object-Oriented Programming
The project demonstrates:

Classes and objects
Encapsulation
Constructors
Getters and setters
Methods
Object relationships
Collections
The application demonstrates how Java collections can be used to store and manipulate objects in memory.

CRUD Design
The project provides practical experience implementing:

Create
Read
Update
Delete
operations.

Service Layer
Business logic is separated from the command-line interface, providing an introduction to layered application design.

Exception and Input Handling
The application provides experience dealing with invalid user input and preventing unexpected application failures.

Automated Testing
TestBookService.java provides an introduction to verifying business logic programmatically rather than relying exclusively on manual testing.

🧩 Example Class Responsibilities
Class	Responsibility
Book	Represents book information
BookService	Performs inventory operations
Main	Handles user interaction
TestBookService	Tests service functionality
Keeping responsibilities separated makes the code easier to understand, test, and extend.

🔧 Troubleshooting
javac: command not found
Java may not be installed or may not be configured in your system's PATH.

Verify:

java -version
javac -version
Install a JDK if necessary.

Could not find or load main class Main
Make sure you compiled the source files:

javac src/*.java
Then run:

java -cp src Main
Also make sure that Main.java contains the application's main method.

Compilation Errors
If compilation fails:

Check the Java version.
Make sure all .java files are present inside src/.
Check for syntax errors.
Ensure class names match their filenames.
Make sure all classes use compatible package declarations.
📌 Example Commands
Compile
javac src/*.java
Run Application
java -cp src Main
Run Tests
java -cp src TestBookService
Clean Compiled Classes
On Linux/macOS:

rm src/*.class
On Windows Command Prompt:

del src\*.class
🤝 Contributing
Contributions and improvements are welcome.

A typical contribution workflow is:

Fork the repository.
Create a feature branch.
git checkout -b feature/improved-search
Make your changes.
Test the application.
Commit your changes.
git commit -m "Improve book search functionality"
Push the branch.
git push origin feature/improved-search
Open a pull request.
When contributing, try to keep business logic inside BookService and user-interface logic inside Main.

📜 License
This project can be distributed and modified according to the license included with the repository.

If no license has been selected yet, consider adding an appropriate open-source license such as the MIT License before publishing the project publicly.

👨‍💻 Project Summary
The Library Book Inventory Management System is a lightweight Java application that demonstrates how a command-line program can manage structured data using object-oriented programming and an in-memory collection.

It provides a practical implementation of:

📕 Book modeling
➕ Creating inventory records
📖 Reading and searching records
✏️ Updating records
🗑️ Deleting records
✅ Input validation
🧪 Automated service testing
🏗️ Basic layered architecture
The project provides a solid foundation that can later be expanded into a database-backed, multi-user library management system or REST API.

