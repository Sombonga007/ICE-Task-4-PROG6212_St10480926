# ICE-Task-4-PROG6212_St10480926


# Contract Claim Data Manager

## 1. Project Overview

The Contract Claim Data Manager is a C# console application developed using .NET 8, Entity Framework Core and SQLite.

The application allows users to manage lecturer claim records, calculate claim amounts, export claim information to a text file and retrieve database information using a direct ADO.NET query.

## 2. What is an ORM?

An Object-Relational Mapper (ORM) is a tool that allows developers to work with database information using objects in a programming language instead of writing SQL statements for every database operation.

Entity Framework Core is an example of an ORM used in this project.

## 3. Entity

An entity is a C# class that represents a table in a database.

In this application, the Claim class represents the Claims table. Its properties represent the information stored for each lecturer claim, such as ClaimId, LecturerName, ModuleCode, HoursWorked and HourlyRate.

## 4. DbContext

DbContext is the main class used by Entity Framework Core to communicate with the database.

The ClaimContext class manages the database connection and allows the application to perform operations such as adding, retrieving, updating and deleting claims.

## 5. DbSet

DbSet represents a collection of entities that can be queried and saved in the database.

The application uses DbSet<Claim> Claims to represent the Claims table. It allows the application to retrieve and manage lecturer claim records.

## 6. Database Provider

A database provider allows Entity Framework Core to communicate with a particular database system.

This application uses the Microsoft.EntityFrameworkCore.Sqlite provider to connect to and manage the SQLite database named claims.db.

## 7. Code First and Database First

### Code First

Code First is an approach where developers create their database structure using C# classes and Entity Framework Core.

The database is then created based on the application's models.

This project uses the Code First approach because the Claim class defines the structure of the Claims table, and EnsureCreated() creates the database when the application starts.

### Database First

Database First is an approach where the database and its tables are created before the application models.

Entity Framework Core can then generate the corresponding C# classes and DbContext from the existing database.

## 8. Data Persistence

The application uses SQLite to store lecturer claim information permanently.

The database is created using Database.EnsureCreated(). Two sample records are inserted only when the Claims table is empty.

Users can add, view, update and delete records through the console menu.

## 9. File Export

The application exports claim information to:

Reports/claim_summary.txt

The report includes lecturer details, claim information, status and calculated total amounts.

StreamWriter is used to write the report, and the completed file is read back and displayed in the console.

## 10. Direct ADO.NET Query

The application also demonstrates direct database access using Microsoft.Data.Sqlite.

SqliteConnection establishes the database connection, while SqliteCommand executes:

SELECT COUNT(*) FROM Claims;

ExecuteScalar() retrieves the number of records stored in the Claims table.

## 11. Technologies Used

- C#
- .NET 8
- Visual Studio
- Entity Framework Core
- Microsoft.EntityFrameworkCore.Sqlite
- Microsoft.Data.Sqlite
- SQLite
- ADO.NET
