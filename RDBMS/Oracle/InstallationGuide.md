<img width="960" height="540" alt="image" src="https://github.com/user-attachments/assets/1a7c27d7-8bc3-46c8-9e46-ac13bd98762c" />
# **Oracle Database Setup on Windows – GUI and CLI**

Before connecting Oracle Database with WebLogic 12c, let's set up Oracle Database properly on your Windows machine.

We'll learn both methods:

1. **GUI method:** Install and configure Oracle Database using graphical tools.
2. **CLI method:** Start, stop, create users, create tables, execute SQL, and manage Oracle Database using Command Prompt and SQL\*Plus.

Since your earlier Windows PATH showed an Oracle Database 26ai installation directory, we'll use Oracle Database 26ai Free as the example, provided that is the version you have installed.

## **1. Understand Oracle Database architecture**

First, understand what gets installed.

**Windows Operating System**

**Oracle Database Software**

Database engine and background processes

**Oracle Database Instance**

Memory (SGA) + background processes

**Database / Pluggable Database**

Tables, schemas, users, records and data files

There are two ways to interact with this database:

- GUI: Oracle SQL Developer.
- CLI: SQL\*Plus.

Both connect to the same Oracle Database.

## **2. Download and install Oracle Database**

[Oracle Database 23 ai free windows 11 에 설치하기 | good](https://images.openai.com/static-rsc-4/zF0hwqbpfFOZxH5P4w9YPM8vUhyb-ed6ftMHCmsaTcIoQ6y6pCYTy6yDEoQBH4OqpUNFGtw8uTuWQLpa2BmHmCxX1ugWS-xI1g4iov7Uvr_acb5cnTXt2L_9b8sG-UzclzONlQdqyc_8MQhuhL0rNSWGlI8efE5zaK_Ef0QNIKI?purpose=inline)

[goodsaem.github.io](https://goodsaem.github.io/hg2exa/?utm_source=chatgpt.com)

Official Oracle resources:

- [Oracle Database Free download](https://www.oracle.com/database/free/?utm_source=chatgpt.com)
- [Oracle SQL Developer download](https://www.oracle.com/database/sqldeveloper/?utm_source=chatgpt.com)

For a learning environment, Oracle Database Free is sufficient for practicing SQL, PL/SQL, schemas, and JDBC connections.

If your existing 26ai installation is working, you do not need to install it again.

## **3. GUI method – Install Oracle Database**

If Oracle Database is not already installed:

**Step 1: Download**

Download the Windows 64-bit ZIP from [Oracle Database 26ai Free](https://www.oracle.com/database/free/get-started/?utm_source=chatgpt.com).

**Step 2: Extract**

Extract the ZIP file to a temporary folder, for example:

```
C:\OracleInstall
```

**Step 3: Run setup**

Open the extracted folder and right-click:

```
setup.exe → Run as administrator
```

[Oracle Database Free - Елфак вики](https://images.openai.com/static-rsc-4/DGd2-NEHeMDaPmv7AXDYiqt0RcvvNZPTzxDLS-nOZHitYpmA3AFlzZIpfeMYgl-e74yjjw-zLavqeDAIRskYOy6EbWuoTMPpBoeIfJ5L_OEDKv-K8rpaSs0cPvZY5VMp9oJ7Ibs7vVhWo8f9dfB0edeGp8bZRSNPQh5atiQ7QAQ?purpose=inline)

[elfak.akymaky.me](https://elfak.akymaky.me/druga/baze/oracle-database-free/?utm_source=chatgpt.com)

**Step 4: Follow the installation wizard**

- Accept the license agreement.
- Complete prerequisite checks.
- Choose an installation directory.
- Set the database administrator password.
- Start the installation.

For Oracle Database 26ai Free, the installer creates a database with SID `FREE`. Its default pluggable database service is `FREEPDB1`.&#x20;

[image](https://www.google.com/s2/favicons?domain=https://docs.oracle.com\&sz=32)

Oracle Docs+1



**Important before installing:** Oracle's 26ai Windows installer requires that certain environment variables, including `ORACLE_HOME` and `TNS_ADMIN`, are not set. It also checks for an existing FREE/XE database service. Do not install over an existing database without checking it first.&#x20;

[image](https://www.google.com/s2/favicons?domain=https://docs.oracle.com\&sz=32)

Oracle Docs



## **4. GUI method – Install SQL Developer**

SQL Developer is the graphical interface used to connect to Oracle Database.

[Connecting SQL Developer to Autonomous Data Warehouse and Creating       Tables](https://images.openai.com/static-rsc-4/kP9cq-N5FRM1TuOnz2qc6KatwvqVwQf8Cg3-Nut-BWOhG7DI98-RcyYYTnFSMm-dJylpiBTmxhjyqEUv6ySLzyApnStjGnUZEgcAmUqKoOqdsW_1aDwHMerIS6OADxhM0Mc00DWl6XPYHA3FqkCJ58Nqy8iobrWzVxnwNeo8CGA?purpose=inline)

[oracle.com](https://www.oracle.com/webfolder/technetwork/tutorials/obe/cloud/adwc/obe_connecting_sql_developer_to_autonomous_data_warehouse_and_creating_tables/connecting_sql_dev_to_adw_and_creating_tables.html?utm_source=chatgpt.com)

Download: [Oracle SQL Developer](https://www.oracle.com/database/sqldeveloper/?utm_source=chatgpt.com)

Installation:

1. Download the Windows ZIP.
2. Extract it to a folder such as `C:\Tools`.
3. Open the extracted `sqldeveloper` folder.
4. Run `sqldeveloper.exe`.

SQL Developer is a database management and SQL development tool; it does not replace the database server.&#x20;

[image](https://www.google.com/s2/favicons?domain=https://www.oracle.com\&sz=32)

Oracle+1



## **5. Connect to Oracle Database using SQL Developer**

Open SQL Developer.

Click the green **+** icon beside Connections.

Enter these example details:

## **New Database Connection**

**Connection Name**

FREE_LOCAL

| Field           | Value                      |
| --------------- | -------------------------- |
| Username        | SYSTEM                     |
| Password        | Your installation password |
| Hostname        | localhost                  |
| Port            | 1521                       |
| Connection Type | Basic                      |
| Role            | Default                    |
| Service Name    | FREEPDB1                   |

Example connection details

Use these details if your database is Oracle Database 26ai Free with its default configuration.

Click **Test**.

Expected:

Status: Success

Click Connect.

You are now connected to Oracle Database through GUI.

## **6. CLI method – Manage Oracle Database using Command Prompt**

Now let's do the same operations without GUI.

This is particularly important for a Database Administrator (DBA).

### **Step 1: Open Command Prompt as Administrator**

Check whether Oracle is installed:

```
where sqlplus
```

Check the Oracle home:

```
echo %ORACLE_HOME%
```

If `where sqlplus` returns a path, SQL\*Plus is available.

If it does not, navigate to your Oracle Database home `bin` folder.

For example:

```
cd C:\app\chila\product\26ai\DBHOME_1\bin
```

Your actual path may differ.

### **Step 2: Check Oracle Windows services**

Press:

```
Windows + R
```

Enter:

```
services.msc
```

Look for Oracle services.

For Oracle Database 26ai Free, typical service names include:

| Service              | Purpose          |
| -------------------- | ---------------- |
| OracleServiceFREE    | Database service |
| Oracle...TNSListener | Network listener |

The listener service name can vary according to installation.

[oracle tns listener - Manjaro dot site](https://images.openai.com/static-rsc-4/z_vcQxOi8u3-Pmz3ILMWVngNwhlDrHxVBoLO-9fO6pwDa_jRUn6cvKtGgdgBzXEu-jImAtwBFPBtJR9I3-F5yOCbYlqGmwIFTllOt_E8bo7n6o7WYDKPi6OriS9z0Lve04f9KOG8VgXFKjxxjDvmVSJsRx_oeQsM64r3jVmuSNY?purpose=inline)

[manjaro.site](https://manjaro.site/how-to-fix-io-errorthe-network-adapter-could-not-establish-the-connection-on-oracle-12c/oracle-tns-listener/?utm_source=chatgpt.com)

If the database service is stopped, start it.

You can also start it from an Administrator Command Prompt:

```
net start OracleServiceFREE
```

### **Step 3: Check the listener**

Execute:

```
lsnrctl status
```

This command checks whether the Oracle listener is running.

The listener normally listens on:

```
HOST: localhost
PORT: 1521
```

If it is stopped, try:

```
lsnrctl start
```

### **Step 4: Connect using SQL\*Plus**

Execute:

```
sqlplus / as sysdba
```

This uses Windows operating-system authentication, assuming your Windows account has the required Oracle DBA privileges.

You should see:

```
Connected to:
Oracle Database ...
```

Oracle documents this local SYSDBA connection method for Oracle Database Free on Windows.&#x20;

[image](https://www.google.com/s2/favicons?domain=https://docs.oracle.com\&sz=32)

Oracle Docs



### **Step 5: Check database status**

Execute:

```
SELECT name, open_mode
FROM v$database;
```

Example output:

```
NAME    OPEN_MODE
------  ----------
FREE    READ WRITE
```

Check pluggable databases:

```
SHOW PDBS;
```

Example:

```
CON_ID  CON_NAME   OPEN MODE
------  ---------  ----------
2       PDB$SEED   READ ONLY
3       FREEPDB1   READ WRITE
```

If `FREEPDB1` is not open, you can open it as SYSDBA:

```
ALTER PLUGGABLE DATABASE FREEPDB1 OPEN;
```

Switch to the pluggable database:

```
ALTER SESSION SET CONTAINER = FREEPDB1;
```

## **7. Create your own database user/schema**

In Oracle, a user owns a schema containing tables, views, procedures, and other objects.

For our WebLogic employee application, let's create a user called `APP_USER`.

Execute these SQL commands while connected to `FREEPDB1` as SYS:

```
CREATE USER APP_USER
IDENTIFIED BY AppPassword123;
```

Give the user basic permissions:

```
GRANT CREATE SESSION,
      CREATE TABLE,
      CREATE VIEW,
      CREATE SEQUENCE,
      CREATE PROCEDURE
TO APP_USER;
```

For a local learning environment, assign a tablespace quota:

```
ALTER USER APP_USER
QUOTA UNLIMITED ON USERS;
```

Now your application user is ready.

APP_USER created

## **8. Connect as APP_USER**

Exit SYS:

```
EXIT;
```

Connect using:

```
sqlplus APP_USER@localhost:1521/FREEPDB1
```

Enter the password when prompted.

You should see:

```
Connected.
SQL>
```

Now you are working as your application database user.

## **9. Create your first table**

Let's create an employee table.

```
CREATE TABLE EMPLOYEES (
    EMPLOYEE_ID NUMBER PRIMARY KEY,
    EMPLOYEE_NAME VARCHAR2(100),
    SALARY NUMBER(10,2),
    DEPARTMENT VARCHAR2(50)
);
```

Insert records:

```
INSERT INTO EMPLOYEES
VALUES (101, 'Rahul', 50000, 'IT');

INSERT INTO EMPLOYEES
VALUES (102, 'Priya', 60000, 'HR');

INSERT INTO EMPLOYEES
VALUES (103, 'Arun', 45000, 'Finance');

COMMIT;
```

Retrieve records:

```
SELECT * FROM EMPLOYEES;
```

Expected output:

| EMPLOYEE_ID | EMPLOYEE_NAME | SALARY | DEPARTMENT |
| ----------- | ------------- | ------ | ---------- |
| 101         | Rahul         | 50000  | IT         |
| 102         | Priya         | 60000  | HR         |
| 103         | Arun          | 45000  | Finance    |

Congratulations! You have created your first Oracle database schema and table.

## **10. Perform the same operations using SQL Developer GUI**

Now open SQL Developer and connect using:

```
Username: APP_USER
Password: AppPassword123
Hostname: localhost
Port: 1521
Service: FREEPDB1
```

Open a SQL Worksheet.

Run:

```
SELECT * FROM EMPLOYEES;
```

You should see the same three employee records.

[Does Oracle SQL Developer refresh when you launch it? - Stack Overflow](https://images.openai.com/static-rsc-4/g7C5WHHW2AIULlp1MSsKcoo4-hyMgFHlGQ2wkOM5izzWMkass1g0OKeaZT6GgsS79aZnT1--uUO70NFbLGq1DgK5Fq1LA-yT3spC5pkZZpNGxWdqf5d7lXYaxuGycay4PsXbKipVLC4sV6wcQxGchmQw1d0rt6TymlXdzx_2lS8?purpose=inline)

[stackoverflow.com](https://stackoverflow.com/questions/73527125/does-oracle-sql-developer-refresh-when-you-launch-it?utm_source=chatgpt.com)

This proves that GUI and CLI are accessing the same database.

## **11. Important Oracle Database commands cheat sheet**

Keep these commands for your practice.

| Task               | Command                                   |
| ------------------ | ----------------------------------------- |
| Check listener     | `lsnrctl status`                          |
| Start listener     | `lsnrctl start`                           |
| Stop listener      | `lsnrctl stop`                            |
| Connect as SYS     | `sqlplus / as sysdba`                     |
| Check database     | `SELECT name FROM v$database;`            |
| Check PDBs         | `SHOW PDBS;`                              |
| Open PDB           | `ALTER PLUGGABLE DATABASE FREEPDB1 OPEN;` |
| Check current user | `SHOW USER;`                              |
| List tables        | `SELECT table_name FROM user_tables;`     |
| Exit SQL\*Plus     | `EXIT;`                                   |

## **12. Your complete environment**

This is the architecture we are building for your WebLogic practice.

## **Windows Oracle Lab Environment**

**Windows 11**

Operating system

**WebLogic 12c**

Admin: 7001Managed: 7003

**Oracle 26ai**

Listener: 1521PDB: FREEPDB1

**Database user: APP_USER**

Employee application schemaTable: EMPLOYEES

**SQL Developer** – GUI access

**SQL\*Plus** – CLI access

## **13. Your first practical task**

Before we proceed to WebLogic JDBC DataSource configuration, let's verify your existing Oracle installation.

Open Command Prompt and execute these three commands:

```
where sqlplus
```

```
lsnrctl status
```

```
sqlplus / as sysdba
```

Then inside SQL\*Plus:

```
SELECT name, open_mode FROM v$database;

SHOW PDBS;
```

**One important thing:** Your earlier PATH showed an Oracle 26ai directory, but that alone does not confirm that the database instance is installed and running. Let's verify it before creating anything new.

Send me the outputs of these commands. I'll guide you using your actual installation paths and database service names rather than assuming they are `FREE` and `FREEPDB1`.

Official references:

- [Oracle 26ai Windows Installation Guide](https://docs.oracle.com/en/database/oracle/oracle-database/26/xeinw/index.html?utm_source=chatgpt.com)
- [Oracle Database Connection Guide](https://docs.oracle.com/en/database/oracle/oracle-database/26/xeinw/connecting-oracle-database-xe.html?utm_source=chatgpt.com)
- [SQL Developer](https://www.oracle.com/database/sqldeveloper/?utm_source=chatgpt.com)
