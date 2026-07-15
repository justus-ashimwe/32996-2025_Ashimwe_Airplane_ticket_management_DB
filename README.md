# Airplane Tickets Management System

## Database Programming Project

### Student Information

* **Student Name:** Ashimwe Bien Aime Justus
* **Student ID:** 32996/2025
* **Course:** Database Programming
* **Project Title:** Airplane Tickets Management System
* **Database:** Oracle Database
* **Language:** SQL & PL/SQL

---

# Project Overview

The **Airplane Tickets Management System** is a relational database application developed using Oracle SQL and PL/SQL. The system automates airline ticket booking and management by storing and processing passenger information, flight schedules, bookings, ticket issuance, payments, aircraft details, airport information, and employee records.

The project demonstrates database design principles, SQL programming, PL/SQL programming, and advanced database programming concepts such as triggers, packages, procedures, functions, cursors, and transaction control.

---

# Problem Statement

Traditional airline ticket management systems often rely on manual processes that result in:

* Duplicate bookings
* Payment errors
* Poor record management
* Slow ticket processing
* Data redundancy
* Difficulty generating reports

This project provides an automated database solution that improves efficiency, accuracy, security, and data integrity.

---

# Project Objectives

* Design a normalized relational database.
* Automate airline booking operations.
* Manage passenger information efficiently.
* Store flight schedules and aircraft information.
* Process ticket bookings and payments.
* Demonstrate SQL and PL/SQL programming concepts.
* Improve data integrity using constraints and triggers.

---
BPMN DIAGRAM


<img width="635" height="386" alt="image" src="https://github.com/user-attachments/assets/d9536a71-8bb6-44bc-ab18-e8f2fc8ea506" />


# System Modules

The system manages:

* Passenger Management
* Aircraft Management
* Airport Management
* Flight Management
* Seat Management
* Booking Management
* Ticket Management
* Payment Management
* Employee Management

---

# Database Design

The project contains the following tables:

1. Passenger
2. Aircraft
3. Airport
4. Flight
5. Seat
6. Booking
7. Ticket
8. Payment
9. Employee
10. Public_Holiday (Reference Table)
11. Audit Table (for activity tracking, if implemented)
    tables created

    <img width="1428" height="850" alt="image" src="https://github.com/user-attachments/assets/c9a7bf38-84c7-4652-bd40-f82e3b40ce98" />


---

# Entity Relationships

* One Passenger can have many Bookings.
* One Flight can have many Bookings.
* One Aircraft can operate many Flights.
* One Aircraft contains many Seats.
* One Booking generates one Ticket.
* One Booking has one Payment.
  ER Diagram

  <img width="1148" height="767" alt="image" src="https://github.com/user-attachments/assets/b2a61784-9589-41a7-b7ee-bad36ab0125b" />


The database is normalized up to **Third Normal Form (3NF)** to reduce redundancy and improve consistency.

---

# Technologies Used

* Oracle Database
* Oracle SQL Developer
* SQL
* PL/SQL

---

# SQL Features Implemented

* CREATE TABLE
* ALTER TABLE
* PRIMARY KEY
* FOREIGN KEY
* UNIQUE Constraints
* CHECK Constraints
* INSERT
* UPDATE
* DELETE
* SELECT
* JOIN Operations

---

# PL/SQL Features Implemented

## Anonymous Blocks

Used to retrieve and display information such as flight details.
<img width="1432" height="853" alt="anonymous block" src="https://github.com/user-attachments/assets/4da777b0-0581-4acc-b740-52d4c0ba6a97" />



## Stored Procedures

Example:

* Book_Flight
  

This procedure creates a new booking.
<img width="1414" height="817" alt="image" src="https://github.com/user-attachments/assets/b98943b0-dc83-428e-822a-b22bdc06d3fa" />


## Functions

Example:

* Calculate_Ticket_Price

Calculates the final ticket price.
<img width="1119" height="700" alt="image" src="https://github.com/user-attachments/assets/b8f6ca87-b4fc-4e58-9214-bdfad3f675ba" />


## Packages

Example:

* Flight_Package

Contains procedures and functions related to flight management.
<img width="1129" height="812" alt="image" src="https://github.com/user-attachments/assets/a5e920d5-e861-4e3d-b601-11609098a7ec" />

## Cursors

Used to display passenger information row by row.

<img width="1429" height="865" alt="cursors" src="https://github.com/user-attachments/assets/d112c3d8-105f-42e5-b62d-0e9c5c3a78fe" />

## Exception Handling

Handles runtime errors such as:

* NO_DATA_FOUND
* DUP_VAL_ON_INDEX
* User-defined exceptions
<img width="1431" height="836" alt="error handling" src="https://github.com/user-attachments/assets/b53eff47-2244-45c3-9686-c7a756571030" />

---

# Advanced Database Programming

## Simple Trigger

Automatically updates booking status after payment.
<img width="1012" height="249" alt="image" src="https://github.com/user-attachments/assets/dac5609f-d5a4-4c8b-b3c3-c666a483527d" />

## Compound Trigger

Can be used to validate multiple booking operations within a transaction.
<img width="757" height="500" alt="image" src="https://github.com/user-attachments/assets/26838243-e986-45e6-b6ba-aa5c93b22e05" />

## Audit System

Tracks user activities including:

* INSERT
* UPDATE
* DELETE

along with:

* Username
* Date
* Time
* Operation performed
  <img width="1147" height="792" alt="image" src="https://github.com/user-attachments/assets/819e481c-9bf9-46e7-862b-bb938c52edd1" />


## Security Restriction

A trigger enforces the following business rule:

Data modification is blocked during:

* Monday to Friday
* Public Holidays

Only weekends are allowed for INSERT, UPDATE, and DELETE operations.

---

# Business Rule

The project implements the following rule:

> Block INSERT, UPDATE, and DELETE operations during weekdays (Monday–Friday) and public holidays stored in the **Public_Holiday** reference table.

This rule is enforced using database triggers.

---

# Transaction Control

The project demonstrates:

* COMMIT
* ROLLBACK

to ensure data consistency.

---

# Window Functions

The project demonstrates Oracle window functions including:

* RANK()
* DENSE_RANK()
* ROW_NUMBER()
* SUM() OVER()
* AVG() OVER()
<img width="1420" height="851" alt="window function" src="https://github.com/user-attachments/assets/f9ebff19-d426-4bcd-a3fc-92bbb2deeaeb" />

These are used for booking reports and payment analysis.

---

# Sample Data

The database contains sample records for:

* Passengers
* Aircraft
* Airports
* Flights
* Seats
* Bookings
* Tickets
* Payments
* Employees
* Public Holidays

---

# Oracle Database Objects

The project includes:

* Tables
* Constraints
* Sequences
* Triggers
* Stored Procedures
* Functions
* Packages
* Cursors

---

# Project Structure

```text
Airplane-Tickets-Management/
│
├── README.md
├── create_tables.sql
├── insert_data.sql
├── procedures.sql
├── functions.sql
├── packages.sql
├── triggers.sql
├── cursors.sql
├── anonymous_blocks.sql
├── window_functions.sql
├── audit.sql
├── business_rules.sql
└── screenshots/
    ├── database_connection.png
    ├── tables.png
    ├── er_diagram.png
    ├── sql_queries.png
    ├── trigger_test.png
    ├── booking_output.png
    └── oem_dashboard.png
```

---

# Installation

1. Install Oracle Database.
2. Install Oracle SQL Developer.
3. Create a database user.
4. Grant the required privileges.
5. Execute `create_tables.sql`.
6. Execute `insert_data.sql`.
7. Execute the PL/SQL scripts.
8. Run the test queries.

---

# Sample Test

```sql
SELECT * FROM Passenger;

SELECT * FROM Flight;

SELECT * FROM Booking;

SELECT * FROM Payment;
```

---

# Expected Results

The system successfully:

* Stores passenger records.
* Manages aircraft and airports.
* Maintains flight schedules.
* Creates bookings.
* Generates tickets.
* Processes payments.
* Tracks user activities.
* Enforces business rules using triggers.
* Supports reporting using window functions.

---

# Future Improvements

Possible enhancements include:

* Web-based booking interface
* Mobile application integration
* Email ticket notifications
* QR-code boarding passes
* Online payment gateway integration
* Flight cancellation and refund management
* Real-time flight tracking
* Dashboard and analytics reports

---

# Conclusion

The Airplane Tickets Management System demonstrates the practical application of Oracle Database concepts, SQL, and PL/SQL to automate airline operations. The project provides a secure, normalized, and efficient database solution that improves booking management, payment processing, and data integrity while satisfying the requirements of a Database Programming course.

---

# Author

**Ashimwe Bien Aime Justus**

Student ID: **32996/2025**

Database Programming Project

Oracle SQL & PL/SQL
