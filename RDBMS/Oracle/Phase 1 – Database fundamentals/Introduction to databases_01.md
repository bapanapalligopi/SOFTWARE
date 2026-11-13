# **Oracle SQL & PL/SQL Course — Day 1**

Day 1

Absolute beginner

2 hours

## **Today’s lesson: Introduction to databases**

Welcome! We’ll start from zero. You do **not** need to know MySQL, SQL, programming, or database concepts before beginning.

By the end of today, you should understand:

- What data and databases are.
- Why databases are used.
- What a DBMS and RDBMS are.
- What Oracle Database is.
- What tables, rows, columns, and records mean.
- The difference between SQL and PL/SQL.
- How a simple business database is organized.

## **1. What is data?**

**Data** means raw facts or information about something.

For example, imagine a college keeps information about its students:

| Student ID | Name  | Age | Course           |
| ---------- | ----- | --- | ---------------- |
| 101        | Rahul | 20  | Computer Science |
| 102        | Priya | 21  | Mathematics      |
| 103        | Amit  | 19  | Physics          |

Each value is data:

- `101` is a student ID.
- `Rahul` is a name.
- `20` is an age.
- `Computer Science` is a course.

When we organize these facts so they can be stored, searched, updated, and managed, we have a useful collection of information.

## **2. What is a database?**

A **database** is an organized collection of related data stored so that it can be accessed and managed efficiently.

Think about a bank. It needs to store:

- Customer names and addresses.
- Account numbers.
- Account balances.
- Deposits and withdrawals.
- Transaction history.

A bank might have millions of customers. Keeping all this information in notebooks or separate text files would be difficult.

A database helps the bank store and manage that information systematically.

["Understanding Databases: A Beginner's Guide" | Anshul E. posted on the topic | LinkedIn](https://images.openai.com/static-rsc-4/Q27GR15o_f4edvbDB36ZRD4-cIUa5AZvhizQ3jt3F86FK3_5LxxGas-4jq5o_p7VVMt8LmYUjRP9m2iiUXPtUkL6ZFF_n1neZO-xyRyDOGfMR_m0DpQd8Q3zibfSAacK1c6lpzWeZoRKegFmrgntcXI5RkhJbHN7o4RcZiR0hYA?purpose=inline)

[linkedin.com](https://www.linkedin.com/posts/anshul-egbert-dass_2-understanding-databases-tables-rows-activity-7365331811691847681-jSqQ?utm_source=chatgpt.com)

**Real-world examples of databases**

| Organization         | Information stored                |
| -------------------- | --------------------------------- |
| Bank                 | Customers, accounts, transactions |
| Hospital             | Patients, doctors, appointments   |
| College              | Students, courses, marks          |
| Online shopping site | Products, customers, orders       |
| Airline              | Passengers, flights, bookings     |

## **3. Why do we need databases?**

Imagine a shop maintains 10,000 customer records in a spreadsheet.

It may face problems:

1. Finding a particular customer's details takes time.
2. The same customer may be entered multiple times.
3. Different employees may accidentally overwrite information.
4. It can be difficult to manage many users at once.
5. Keeping information accurate and secure becomes challenging.

A database system helps address these problems.

Its main benefits include:

- **Organized storage:** Data is stored in a structured way.
- **Fast searching:** Find information without checking every record manually.
- **Data security:** Control who can access or change information.
- **Data consistency:** Apply rules to keep information valid.
- **Multi-user access:** Multiple authorized users can work with data.
- **Backup and recovery:** Help restore information after failures.

## **4. What is a DBMS?**

DBMS stands for **Database Management System**.

It is software that helps users create, store, retrieve, update, and manage databases.

Think of it this way:

- Database = the organized information.
- DBMS = the software that manages that information.

Examples of database management systems include:

- Oracle Database
- MySQL
- Microsoft SQL Server
- PostgreSQL
- SQLite

[Getting Started with DBMS](https://images.openai.com/static-rsc-4/qZVqKtruRE_bNnfVzhZxMSXnhvpP4K7o9qBkBPpLu7tzYQJ9WCFcbSsqD_PeHXbBQbOey3U4un-pAjSQy1t6FDS5PvgUhj6Mi-FPWy4auCC3qF6BhH2qz75rUbro7TP3sglY5v15OZeBm4G3y5-Dua1naGk1J9LTs_1zyNmW5qE?purpose=inline)

[blog.codingminutes.com](https://blog.codingminutes.com/introduction-to-dbms?utm_source=chatgpt.com)

**Simple example**

A bank employee wants to check a customer's account balance.

1. The employee uses a banking application.
2. The application requests account information.
3. The DBMS processes the request.
4. The database provides the stored information.
5. The application displays the balance.

You do not need to understand the technical details yet. We will learn how to retrieve information using SQL later.

## **5. What is an RDBMS?**

RDBMS stands for **Relational Database Management System**.

It is a type of database management system that organizes data into related tables.

For example, a college database might contain:

**STUDENTS table**

| STUDENT_ID | NAME  | COURSE_ID |
| ---------- | ----- | --------- |
| 101        | Rahul | 10        |
| 102        | Priya | 20        |
| 103        | Amit  | 10        |

**COURSES table**

| COURSE_ID | COURSE_NAME      |
| --------- | ---------------- |
| 10        | Computer Science |
| 20        | Mathematics      |

Notice that both tables contain `COURSE_ID`.

This shared value allows the database to connect students with their courses. This is the basic idea behind relationships in relational databases.

[All The MySQL Keys Explained ! | CodeX](https://images.openai.com/static-rsc-4/fvm6pJB4fuIPOsoTe-ipgLgkJHTIdlvD8mCbrhNz3q1clD2bD6aGUTUKZl1O4gYrguPhQp2iFDjs4Sfkn5f5B-QkqAZV1EHTbwy5tgimI0qqxNGFdffnSo9PNp_DJeIyOMTS_dF2X3Gg9ED2SL8hLaYhwzoc49-Tuz4JYRg0d3s?purpose=inline)

[medium.com](https://medium.com/codex/mysql-keys-that-you-did-not-know-earlier-ec0026ceb945?utm_source=chatgpt.com)

Oracle Database is an RDBMS.

Other examples include MySQL, PostgreSQL, and Microsoft SQL Server.

## **6. Understanding tables, rows, and columns**

This is one of the most important concepts in your Oracle journey.

Consider this table:

**EMPLOYEES**

| EMPLOYEE_ID | EMPLOYEE_NAME | SALARY | DEPARTMENT |
| ----------- | ------------- | ------ | ---------- |
| 1           | John          | 30000  | HR         |
| 2           | Mary          | 45000  | IT         |
| 3           | David         | 40000  | Finance    |

[SQL Interview Cheat Sheet |   LearnSQL.com](https://images.openai.com/static-rsc-4/Kiho4Ian2wGonBKto9v66xpPZO_vWLfz6RicG7bketF-ibnNap0gvA2qqD4INZWNXt63MakVshDbcnUzgmJ5ywk5t60IMSgddTS2iTS09McLoyh8_qED4v4U7RMNSZpB4cg3ghlPiQDbBUg4IncXtdIjDAe-SS9H0BdBliPxNtE?purpose=inline)

[learnsql.com](https://learnsql.com/blog/sql-interview-cheat-sheet/?utm_source=chatgpt.com)

Understand these terms:

**Table:** A structure used to organize related data. Here, `EMPLOYEES` is the table name.

**Column:** A particular type of information. `EMPLOYEE_NAME`, `SALARY`, and `DEPARTMENT` are columns.

**Row:** One complete entry in the table. John's employee information is one row.

**Cell:** One individual value at the intersection of a row and column. John's salary, `30000`, is one cell.

**Record:** Another common word for a row.

**Field:** Another common word for a column, although the exact usage can vary by context.

Remember:

- Table = collection of rows and columns.
- Row = one record.
- Column = one attribute.
- Cell = one value.

## **7. What is Oracle Database?**

[Oracle Database in Dubai, UAE](https://images.openai.com/static-rsc-4/0qRtJzDzHUoRVWdCWp4xcusTkf2NmSUhbyGQdXw7Px4bCZzaLukSlLhe3AET2rcMd-PV1XT3B07nJN_sFrxTbe78cxrfQinun22Wx2JO-Jm5IRj-tW0SXrIehqUgG9-wjwNY_QSPtKFv0E1wxyX0UkVjUQNoNtqr5EhsR63cvhw?purpose=inline)

**Oracle Database**

A relational database management system developed by Oracle.

Used in banking, healthcare, retail, telecom, and enterprise applications.

Oracle Database helps organizations store and manage large amounts of information.

For example, a banking system might use Oracle to manage:

- Customer information.
- Bank accounts.
- Transactions.
- Loan information.
- Payment records.

In this course, you will learn two important technologies:

**Oracle SQL**

SQL stands for Structured Query Language. It is used to communicate with a database.

Examples of what SQL can do:

- Retrieve employee details.
- Add a new customer.
- Update an employee's salary.
- Delete a record when permitted.

**PL/SQL**

PL/SQL stands for Procedural Language/SQL. It is Oracle's programming language extension to SQL.

It allows you to write programs containing:

- Variables.
- Conditions.
- Loops.
- Procedures.
- Functions.
- Exception handling.

Think of it this way:

| SQL                                 | PL/SQL                                                |
| ----------------------------------- | ----------------------------------------------------- |
| Retrieves and modifies data         | Adds programming logic                                |
| Executes SQL statements             | Executes blocks of code                               |
| Example: retrieve employee salaries | Example: calculate bonuses using conditions and loops |

We will learn SQL first and then gradually move into PL/SQL.

## **8. What is SQL? A first look**

SQL is the language used to communicate with a relational database.

Imagine you want to see all employees in the `EMPLOYEES` table.

You can write:

```
SELECT *
FROM employees;
```

Don't worry if you don't understand the syntax yet. We'll learn it properly in upcoming lessons.

For now, understand:

- `SELECT` means retrieve information.
- `*` means all columns.
- `FROM employees` means get information from the employees table.

Another example:

```
SELECT employee_name, salary
FROM employees;
```

This requests only the employee names and salaries.



Remember

&#x20;SQL is a language, not a database. Oracle Database is the software that stores and manages data; SQL is one way to communicate with it.



## **9. What is a database schema?**

A **schema** is a collection of database objects associated with a database user.

These objects can include:

- Tables
- Views
- Indexes
- Sequences
- Procedures
- Functions
- Packages

For example, imagine a company has an HR schema containing:

```
HR
 |
 +-- EMPLOYEES
 +-- DEPARTMENTS
 +-- JOBS
 +-- EMPLOYEE_DETAILS
```

In Oracle, a schema is associated with a database user. We will explore users, schemas, and database objects in more detail later.

## **10. SQL vs MySQL vs Oracle**

As a beginner, it is important to understand these names.

| Name            | Meaning                                          |
| --------------- | ------------------------------------------------ |
| SQL             | A language for working with relational databases |
| MySQL           | A relational database management system          |
| Oracle Database | Another relational database management system    |
| PL/SQL          | Oracle's procedural extension to SQL             |

You do not need to learn MySQL before learning Oracle.

You can start directly with Oracle SQL and PL/SQL.

## **11. Your first practical database example**

Let's create a simple imaginary employee database in our minds.

**Company: ABC Technologies**

It has three employees:

| ID  | Name  | Salary | Department |
| --- | ----- | ------ | ---------- |
| 101 | Arun  | 25000  | HR         |
| 102 | Sneha | 40000  | IT         |
| 103 | Kiran | 35000  | Finance    |

Now consider these business requirements:

| Requirement               | What the database needs to do |
| ------------------------- | ----------------------------- |
| Show all employees        | Retrieve records              |
| Add a new employee        | Insert a record               |
| Change Arun's salary      | Update a record               |
| Remove an employee record | Delete a record               |
| Show only IT employees    | Filter records                |
| Calculate average salary  | Perform a calculation         |

These are common tasks performed using SQL.

Later, you will learn how to write the actual SQL statements for every requirement.

## **12. Day 1 practice exercises**

Try answering these questions without looking at the answers first.

**Day 1 knowledge check**

0 / 8 answered

**1. What is a database?**

A programming language

An organized collection of data

An operating system

**2. What does DBMS stand for?**

Database Management System

Data Backup Management Software

Database Machine System

**3. Which of these is an RDBMS?**

Oracle Database

Microsoft Word

Windows

**4. In a database table, what is a row?**

A column heading

One complete record

A database user

**5. What does SQL stand for?**

Structured Query Language

Simple Question Language

System Query Logic

**6. Do you need to know MySQL before learning Oracle SQL?**

Yes

No

**7. What is PL/SQL?**

A type of computer hardware

Oracle's procedural extension to SQL

Another name for MySQL

**8. In a table, what is a column?**

A type of information or attribute

A complete record

The database itself

Check my answers

## **13. Interview questions and answers**

These are beginner-level interview questions. Read the answers and try explaining them in your own words.

**Q1. What is a database?**

A database is an organized collection of related data that can be stored, accessed, and managed efficiently.

**Q2. What is DBMS?**

DBMS stands for Database Management System. It is software used to create, maintain, and manage databases.

**Q3. What is RDBMS?**

RDBMS stands for Relational Database Management System. It stores data in tables and allows relationships between tables.

**Q4. What is the difference between DBMS and RDBMS?**

DBMS is the broader category of database management software. RDBMS is a type of DBMS that organizes data using related tables.

**Q5. What is Oracle Database?**

Oracle Database is a relational database management system developed by Oracle Corporation.

**Q6. What is SQL?**

SQL stands for Structured Query Language. It is used to retrieve and manipulate data in relational databases.

**Q7. What is PL/SQL?**

PL/SQL is Oracle's procedural extension to SQL. It supports variables, conditions, loops, procedures, functions, and exception handling.

**Q8. What is a table?**

A table is a database object that stores data in rows and columns.

**Q9. What is a record?**

A record is one complete row of information in a table.

**Q10. Can we learn Oracle without knowing MySQL?**

Yes. MySQL and Oracle are different database systems. Knowledge of MySQL is not required to begin learning Oracle.

## **14. Day 1 assignment**

Your homework

Complete these tasks in a notebook or document.

**Task 1: Write definitions**

Write your own definitions for:

1. Data
2. Database
3. DBMS
4. RDBMS
5. Oracle Database
6. SQL
7. PL/SQL
8. Table
9. Row
10. Column

**Task 2: Design a student table**

Create a sample table on paper with these columns:

- STUDENT_ID
- STUDENT_NAME
- AGE
- CITY
- COURSE

Enter at least five imaginary student records.

Example:

| STUDENT_ID | STUDENT_NAME | AGE | CITY      | COURSE |
| ---------- | ------------ | --- | --------- | ------ |
| 1          | Rahul        | 20  | Hyderabad | SQL    |
| 2          | Priya        | 21  | Chennai   | Java   |
| 3          | Amit         | 22  | Pune      | Python |
| 4          | Neha         | 20  | Mumbai    | SQL    |
| 5          | Ravi         | 23  | Delhi     | Java   |

**Task 3: Think like a database developer**

Imagine you are developing a database for a hospital.

Write down five tables you might need.

For example:

- PATIENTS
- DOCTORS
- APPOINTMENTS

Think of two more.

**Task 4: Explain the concepts**

Try explaining the difference between SQL and PL/SQL in your own words, as if you were answering an interviewer.

## **15. Your 2-hour Day 1 schedule**

| Time       | Activity                                      |
| ---------- | --------------------------------------------- |
| 30 minutes | Read and understand today's concepts          |
| 20 minutes | Study the employee and student table examples |
| 20 minutes | Complete the knowledge check                  |
| 20 minutes | Prepare interview answers                     |
| 20 minutes | Complete the assignment                       |
| 10 minutes | Revise the key terms                          |

## **16. What comes next?**

**Day 2: Introduction to Oracle Database**

Next lesson

[SQL Developer: Contoh Penggunaan dan Koneksi ke Database](https://images.openai.com/static-rsc-4/F_XyiePzgaCShfDDwpQVLFCWFV3prs2eE-1yTwaekYO34ttBXWwURAXyE_AE3t4SauMOQsrSD2pKX9tIrZyhWYegUQhiwEwNnukGr3MoCK5CynoEYWtGyWXz7KJnyiFHmQUjf-D9RMxdXOcmBBiPPI93_RfHN2B4yauTgvIgqHE?purpose=inline)

[revou.co](https://revou.co/panduan-teknis/sql-developer?utm_source=chatgpt.com)

You will learn:

- Oracle Database architecture at a beginner level.
- Oracle Database vs Oracle SQL Developer.
- What a database user and connection mean.
- What schemas and database objects are.
- How to install or access an Oracle learning environment.
- How to prepare your computer for practical SQL exercises.

**Today's key takeaway:** You do not need any previous database knowledge to become an Oracle SQL and PL/SQL Developer. Start with the fundamentals, practise consistently, and build your skills one lesson at a time.

When you're ready, say **"Start Day 2"** and we'll continue from the basics.
