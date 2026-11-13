# **Oracle SQL & PL/SQL Course — Day 2**

Day 2

Absolute beginner

2 hours

## **Today's topic: Introduction to Oracle Database**

Yesterday, you learned what data, databases, DBMS, RDBMS, tables, rows, columns, SQL, and PL/SQL mean.

Today, we'll understand **how Oracle Database works, what Oracle SQL Developer is, how users and schemas work, and how to prepare for hands-on practice.**

No MySQL or programming knowledge is required.

## **1. What exactly is Oracle Database?**

[Oracle DataBase Enterprise Edition](https://images.openai.com/static-rsc-4/MAD_OixjnJKShdjBwH7Cp_XBcVd2j47Gw0_EtlJryqE9bcUaqDrYAwrjv2SgvHvJilu_FKsRQ-ZXFFoSFMRsNM4uReG09EtoHSCv82PlDCPtncI-SrNxjM3b6prqaYdYM5FzKVfMryf88wZit5yU137XTlGEN8Wvl2hEDVDpCY0?purpose=inline)

**Oracle Database**

Software used to store, organize, retrieve, and manage information.

Imagine a company called ABC Technologies.

It has:

- 500 employees.
- 20 departments.
- 100 customers.
- Thousands of transactions.

The company needs a reliable place to store and manage all this information.

Oracle Database can manage this information.

For example:

**EMPLOYEES table**

| EMP_ID | EMP_NAME | SALARY |
| ------ | -------- | ------ |
| 101    | Arun     | 30000  |
| 102    | Priya    | 40000  |
| 103    | Ravi     | 35000  |

The company can use SQL to retrieve information from this table.

```
SELECT *
FROM employees;
```

This retrieves all columns and rows from the `EMPLOYEES` table.

## **2. How does Oracle Database work?**

Let's understand this with a simple example.

Imagine you work as an employee in a bank.

You open a banking application and search for a customer's account balance.

What happens behind the scenes?

[Differences Between Mobile App and Web App Testing | Testlio](https://images.openai.com/static-rsc-4/ORXLCOFG0XY6oaFzH6yABtaPnjiv4tTKUVLHVLRBCA0S6PKQCQwNVZ53rh_1ZBrVtf2vCeJHKtcCcazIzIS5_SphrLL0cWKXEZ59R-c40IB7iILBkR4teRQigFMC9VNnWuAC8j7ni8LT_SfPObnC305DuI7s_PJMsv7bv3KjO58?purpose=inline)

[testlio.com](https://testlio.com/blog/desktop-vs-web-vs-mobile-app-testing?utm_source=chatgpt.com)

The basic process is:

1. You enter a request in an application.
2. The application sends the request to Oracle Database.
3. Oracle processes the request.
4. Oracle retrieves the required information.
5. The result is returned to the application.

For example, an application might send:

```
SELECT balance
FROM accounts
WHERE account_id = 1001;
```

Oracle finds the matching account and returns its balance.

**Important terms:**

- Client: The application or tool that sends a request.
- Database server: The system running Oracle Database.
- Query: A request to retrieve or work with data.
- Result: The information returned by the database.

## **3. Oracle Database vs SQL Developer**

This is a very important distinction for beginners.

[Oracle Database in Dubai, UAE](https://images.openai.com/static-rsc-4/0qRtJzDzHUoRVWdCWp4xcusTkf2NmSUhbyGQdXw7Px4bCZzaLukSlLhe3AET2rcMd-PV1XT3B07nJN_sFrxTbe78cxrfQinun22Wx2JO-Jm5IRj-tW0SXrIehqUgG9-wjwNY_QSPtKFv0E1wxyX0UkVjUQNoNtqr5EhsR63cvhw?purpose=inline)

**Oracle Database**

The actual database software. It stores and manages your data and executes SQL statements.

[SQL Developer on macOS Ventura 13.4.1 on M2 (Silicon) - Oracle Forums](https://images.openai.com/static-rsc-4/yh4E4QtPx9VFzYGJAWaInVnSU8hn9sAku0OwJNPODsJdO3HjYL9RSAPCc2zmhLzTVyndaXplmw_rFDcQaE-BSoVpQn49cpBU2FzlqxA8HoiiivwZQhvxU9AQKFktWsNdT6-9-n-m4I-KXnWPjpPjKoukHcGtCvbMD54VC9NpLGY?purpose=inline)

**Oracle SQL Developer**

A graphical application that helps developers connect to Oracle Database, write SQL, run queries, and manage database objects.

Think of it this way:

- Oracle Database = A kitchen where food is prepared.
- SQL Developer = The interface you use to give instructions to the kitchen.

SQL Developer does not replace Oracle Database. It connects to it.

You can also use other tools to connect to Oracle Database.

## **4. What is an Oracle database instance?**

You will hear the word **instance** frequently in Oracle interviews.

An Oracle instance is the combination of:

1. Memory structures.
2. Background processes.

These work together to access and manage an Oracle database.

[File:Oracle-database-architecture revised.svg - Wikimedia Commons](https://images.openai.com/static-rsc-4/im0n0Oc2WVSZ5Zmj3xnBwE6vjzftivA6V_39B1fmBwjwtvd5DpC07D6kzVbNa0ttJUI4PbXnnzZhEObaFVxOmQ0efzfBpX0tT4_mqPx2Jla4GkLm6mp80Thka_AhYEBiBqfp52HOktzHLvkUGzzqp2MRkgvRnk9Z0vq4gtSpd7I?purpose=inline)

[commons.wikimedia.org](https://commons.wikimedia.org/wiki/File%3AOracle-database-architecture_revised.svg?utm_source=chatgpt.com)

Let's understand the basic components.

**A. Memory structures**

Oracle uses memory to process database operations efficiently.

One important memory structure is the SGA.

SGA stands for **System Global Area**.

It is shared memory used by the Oracle instance.

Some important SGA components are:

- Database Buffer Cache: Stores copies of database blocks in memory.
- Shared Pool: Stores information such as parsed SQL and data dictionary information.
- Redo Log Buffer: Temporarily holds redo information describing changes.

Don't memorize all the technical details today. Just remember that the SGA is shared memory used by the instance.

**B. Background processes**

Oracle uses background processes to perform internal work.

Examples:

| Process | Basic purpose                                          |
| ------- | ------------------------------------------------------ |
| DBWn    | Writes modified database blocks to data files          |
| LGWR    | Writes redo information to redo log files              |
| CKPT    | Coordinates checkpoint operations                      |
| SMON    | Performs system monitoring and instance recovery tasks |
| PMON    | Handles cleanup after failed user processes            |

For Day 2, focus on remembering the names and their general responsibilities.

## **5. Oracle Database vs Oracle Instance**

These terms are often confused.

| Oracle Database                                | Oracle Instance                   |
| ---------------------------------------------- | --------------------------------- |
| Physical files that store database information | Memory and background processes   |
| Contains data files, control files, redo logs  | Uses SGA and background processes |
| Stores persistent information                  | Manages access to the database    |

A simple way to remember:

**Database = Files**

**Instance = Memory + Processes**

Together, the instance and database work to provide access to stored information.

## **6. What is a database user?**

A database user is an account used to connect to an Oracle Database.

For example, a company might have these users:

| Username | Purpose                     |
| -------- | --------------------------- |
| HR       | Human Resources information |
| SALES    | Sales information           |
| FINANCE  | Financial information       |
| ADMIN    | Database administration     |

Each user has permissions that determine what they can do.

For example:

- One user may be allowed to view employee records.
- Another may be allowed to insert and update records.
- An administrator may have broader privileges.

A user normally connects using credentials and a database connection configuration.

**Important:** A database user is not necessarily the same thing as a person. An application can also use a database account.

## **7. What is a schema?**

A schema is a collection of database objects owned by a database user.

For example, imagine the `HR` user owns these objects:

```
HR (SCHEMA)
 |
 +-- EMPLOYEES
 |
 +-- DEPARTMENTS
 |
 +-- JOBS
 |
 +-- LOCATIONS
 |
 +-- PROCEDURES
```

The tables, views, procedures, and other objects owned by HR belong to the HR schema.

In Oracle, a schema has the same name as its owning user.

For example:

- User: HR
- Schema: HR

**Interview point:** A schema is a logical collection of database objects owned by a database user. It is not a separate physical database.

## **8. What are database objects?**

A database object is something created and stored inside a database schema.

Here are the important Oracle database objects you will learn throughout this course:

| Object    | Purpose                                                   |
| --------- | --------------------------------------------------------- |
| Table     | Stores data in rows and columns                           |
| View      | Displays data from one or more tables                     |
| Index     | Helps retrieve data efficiently                           |
| Sequence  | Generates numbers, often used for IDs                     |
| Synonym   | Provides an alternative name for an object                |
| Procedure | Stores a reusable PL/SQL program                          |
| Function  | Stores a program that can return a value                  |
| Package   | Groups related PL/SQL procedures and functions            |
| Trigger   | Runs automatically when a specified database event occurs |

For example, an HR schema might contain:

```
HR
 |
 +-- TABLES
 |    +-- EMPLOYEES
 |    +-- DEPARTMENTS
 |
 +-- VIEWS
 |    +-- EMPLOYEE_DETAILS
 |
 +-- SEQUENCES
 |    +-- EMPLOYEE_SEQ
 |
 +-- PROCEDURES
      +-- UPDATE_SALARY
```

We'll create and use these objects in upcoming lessons.

## **9. What is a database connection?**

Before writing SQL, you need to connect to an Oracle Database.

A connection tells your SQL tool which database to contact and which user to connect as.

Usually, you need these details:

| Detail       | Meaning                                | Example              |
| ------------ | -------------------------------------- | -------------------- |
| Username     | Database account                       | HR                   |
| Password     | Account password                       | Your chosen password |
| Hostname     | Computer or server running Oracle      | localhost            |
| Port         | Network communication port             | 1521                 |
| Service name | Identifies the Oracle database service | FREEPDB1             |

These are example values, not universal settings. Your actual connection details depend on your Oracle installation.

**What do these terms mean?**

- `localhost`: Your own computer.
- `1521`: Oracle's commonly used listener port.
- `FREEPDB1`: A common default pluggable database service name in Oracle Database Free installations.

### **What is a service name?**

A service name identifies a database service to which your client connects.

For example, an Oracle Database Free installation commonly provides a pluggable database service named `FREEPDB1`.

You may also see `ORCLPDB1` in other Oracle installations.

Don't confuse a service name with a username. They identify different things.

## **10. What is a CDB and PDB?**

Oracle uses a multitenant architecture.

You will encounter two terms:

- CDB: Container Database.
- PDB: Pluggable Database.

[Multitenant : Overview of Container Databases (CDB) and Pluggable Databases (PDB) - ORACLE-BASE](https://images.openai.com/static-rsc-4/-8mmhhUgF_DvJTQ-CdkCnuJ90QqmPDRF5GkJMjCsOWffa7yaUYrm2U3oHmdPMe0huEEQg3kWBbgFxuwgcuvssarbKTlaMlLe5w8qMRFVuUylZmp2-cKtgXoexZw__3toSaTHqij12SlP4sPEGXk6ZJse6AYM1kCmKFtzfSI40q4?purpose=inline)

[oracle-base.com](https://oracle-base.com/articles/12c/multitenant-overview-container-database-cdb-12cr1?utm_source=chatgpt.com)

Think of a CDB as a large container that can hold multiple PDBs.

A PDB is a database environment that can contain its own application data and schemas.

Example:

```
CDB
 |
 +-- CDB$ROOT
 |
 +-- PDB$SEED
 |
 +-- FREEPDB1
 |
 +-- SALES_PDB
```

What are these?

- `CDB$ROOT`: The root container, which holds system-wide metadata and common information.
- `PDB$SEED`: A template used to create new PDBs.
- `FREEPDB1`: An example pluggable database.
- `SALES_PDB`: An imaginary PDB created for a sales application.

For now, remember that a PDB is where you will commonly work with application schemas and tables in a modern Oracle installation.

## **11. Prepare your Oracle learning environment**

You have two beginner-friendly options.

**Option A: Oracle Live SQL**

Easiest to start

[Live SQL](https://images.openai.com/static-rsc-4/kF0tz56uir7FNHTP07K0621jIpsAyIHR9VQE5jzt4wz46-9WLxrBW6UoL_SRQjkwye1e4tzJMoPhTVtZIbmoDwi_9GfoyI9FxvcFN2sAqA7y4qgbdBf2tYbWYuimF2VRunN9-LOsZTOiYrEvE78IuO_DINVAB9T74iiBvlOS1XY?purpose=inline)

[oracle.com](https://www.oracle.com/technetwork/cn/database/application-development/livesql/index.html?utm_source=chatgpt.com)

Browser-based Oracle SQL practice environment. You don't need to install a local database to start practising.

**How to start:**

1. Open [Oracle Live SQL](https://livesql.oracle.com/?utm_source=chatgpt.com).
2. Sign in or follow the site's account instructions.
3. Open the SQL worksheet.
4. You can start practising SQL statements there.

   Open Oracle Live SQL&#x20;

   **Option B: Install Oracle Database Free + SQL Developer**

   [Connecting SQL Developer to Autonomous Data Warehouse and Creating       Tables](https://images.openai.com/static-rsc-4/kP9cq-N5FRM1TuOnz2qc6KatwvqVwQf8Cg3-Nut-BWOhG7DI98-RcyYYTnFSMm-dJylpiBTmxhjyqEUv6ySLzyApnStjGnUZEgcAmUqKoOqdsW_1aDwHMerIS6OADxhM0Mc00DWl6XPYHA3FqkCJ58Nqy8iobrWzVxnwNeo8CGA?purpose=inline)

   [oracle.com](https://www.oracle.com/webfolder/technetwork/tutorials/obe/cloud/adwc/obe_connecting_sql_developer_to_autonomous_data_warehouse_and_creating_tables/connecting_sql_dev_to_adw_and_creating_tables.html?utm_source=chatgpt.com)

   A local setup that lets you practise connecting to and working with an Oracle database on your computer.

   **You will need:**
5. Oracle Database Free — the database software.
6. Oracle SQL Developer — the graphical tool for writing and running SQL.
7. A database username and password.

   Oracle Database Free&#x20;

   For our learning exercises, Oracle Database 26ai Free is a suitable starting point. Many core SQL and PL/SQL concepts also apply to Oracle 19c.

**My recommendation:** Start with Oracle Live SQL if you want to begin immediately. Later, set up Oracle Database Free and SQL Developer so you can practise database connections and administration locally.

## **12. Your first SQL practice — safely**

Today, we will only look at a simple query. We'll learn how to create tables and insert data in detail in later lessons.

Try this in Oracle Live SQL:

```
SELECT 'WELCOME TO ORACLE SQL' AS MESSAGE
FROM DUAL;
```

Expected output:

| MESSAGE               |
| --------------------- |
| WELCOME TO ORACLE SQL |

What is `DUAL`?

`DUAL` is a special one-row table available in Oracle. It is commonly used when you want to evaluate an expression or display a value without querying your own business table.

For example:

```
SELECT 10 + 20 AS TOTAL
FROM DUAL;
```

Expected output:

| TOTAL |
| ----- |
| 30    |

Another example:

```
SELECT SYSDATE AS TODAY
FROM DUAL;
```

This displays the database server's current date and time.

**Today's practical goal:** Run these three queries and understand what each one returns. You do not need to memorize every detail yet.

## **13. Day 2 knowledge check**

Try these questions before reading the answers.

**10-question quiz**

0/10 answered

**1. Which software actually stores and manages database information?**

SQL Developer

Oracle Database

Microsoft Word

**2. What is Oracle SQL Developer?**

A tool to connect to Oracle and run SQL

The database itself

A programming language

**3. What does an Oracle instance consist of?**

Tables and columns

Memory structures and background processes

Only data files

**4. What does SGA stand for?**

System Global Area

SQL General Application

System Generated Account

**5. Which background process writes redo information to redo log files?**

DBWn

LGWR

PMON

**6. What is a schema?**

A collection of database objects owned by a user

A computer's operating system

A network port

**7. What is the common Oracle listener port?**

80

1521

3306

**8. What does PDB stand for?**

Personal Database Backup

Pluggable Database

Program Database

**9. What is localhost?**

Your own computer

A database username

A SQL command

**10. What is DUAL used for in Oracle?**

To delete tables

To evaluate expressions or display values

To create users

Submit quiz

## **14. Day 2 interview questions and answers**

**Q1. What is Oracle Database?**

Oracle Database is a relational database management system used to store, retrieve, and manage data.

**Q2. What is SQL Developer?**

SQL Developer is a graphical tool used to connect to Oracle Database, write SQL statements, execute queries, and manage database objects.

**Q3. What is an Oracle instance?**

An Oracle instance consists of memory structures and background processes that manage access to an Oracle database.

**Q4. What is SGA?**

SGA stands for System Global Area. It is shared memory used by an Oracle instance.

**Q5. What is the difference between an Oracle database and an instance?**

The database consists of physical files that store information. The instance consists of memory structures and background processes that access and manage those files.

**Q6. What is a database user?**

A database user is an account that can connect to an Oracle Database and perform operations according to its privileges.

**Q7. What is a schema?**

A schema is a collection of database objects owned by a database user.

**Q8. What is a PDB?**

A PDB, or Pluggable Database, is a portable database environment within an Oracle multitenant container database.

**Q9. What is the purpose of LGWR?**

LGWR writes redo information from the redo log buffer to online redo log files.

**Q10. What is the difference between SQL Developer and Oracle Database?**

Oracle Database stores and manages data. SQL Developer is a client application that connects to Oracle Database and allows users to work with it.

## **15. Day 2 assignment**

Complete these tasks in your notebook.

**Task 1 — Explain in your own words**

Write a short explanation of:

1. Oracle Database
2. Oracle SQL Developer
3. Oracle instance
4. SGA
5. Database user
6. Schema
7. CDB
8. PDB

**Task 2 — Match the terms**

| Term            | Match with |
| --------------- | ---------- |
| Oracle Database | ?          |
| SQL Developer   | ?          |
| SGA             | ?          |
| LGWR            | ?          |
| Schema          | ?          |
| PDB             | ?          |

Use these descriptions:

- A. Collection of objects owned by a user
- B. Shared memory area
- C. Pluggable Database
- D. Stores and manages data
- E. Writes redo information
- F. Tool used to connect and run SQL

**Task 3 — Practical exercise**

If you can access Oracle Live SQL, execute:

```
SELECT 'MY FIRST ORACLE QUERY' AS MESSAGE
FROM DUAL;

SELECT 100 + 200 AS TOTAL
FROM DUAL;

SELECT SYSDATE AS TODAY
FROM DUAL;
```

Write down what each query returns.

**Task 4 — Think like an Oracle developer**

A company has HR, SALES, and FINANCE departments.

Answer:

- What database users might the company create?
- What tables might HR need?
- Why should each user have appropriate permissions?

## **16. Day 2 revision notes**

**Remember these key points**

- Oracle Database stores and manages data.
- SQL Developer is a tool used to work with Oracle.
- An instance = memory structures + background processes.
- SGA = System Global Area.
- DBWn writes modified database blocks to data files.
- LGWR writes redo information to redo log files.
- A schema contains objects owned by a user.
- CDB = Container Database.
- PDB = Pluggable Database.
- DUAL is a special one-row Oracle table.

## **17. What you will learn on Day 3**

Next lesson

**Day 3 — Introduction to SQL and SQL commands**

[SQL DML Commands | Commands of DML with Examples](https://images.openai.com/static-rsc-4/4aatkdG2eipy1rnkK0OI-RCpzNW37IwylcedcsEi0Ph1qkpQjZTdiYXn1vLB67XiKhkBPx2hSG6Mm9-fsztHtBzM6np2UrhImM5Hxk1L53n3SAKiFZhZhzKD69P-feVPcUBZv-6xoP85lvcR1ik3KcQZt-QNYpP4Y2h8eqblyv4?purpose=inline)

[educba.com](https://www.educba.com/sql-dml-commands/?utm_source=chatgpt.com)

Topics:

1. What is SQL in detail?
2. SQL statement structure.
3. Categories of SQL commands.
4. DDL — Data Definition Language.
5. DML — Data Manipulation Language.
6. DQL — Data Query Language.
7. DCL — Data Control Language.
8. TCL — Transaction Control Language.
9. Your first `SELECT` statement.

**Your target today:** Understand the difference between Oracle Database, Oracle SQL Developer, an instance, a user, and a schema. These concepts will make the practical SQL lessons much easier.

When you're ready, say **"Start Day 3"**.
