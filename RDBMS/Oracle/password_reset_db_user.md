The error `ORA-01017` means Oracle rejected the username/password combination. `gopi`**&#x20;and&#x20;**`root`**&#x20;are not automatically Oracle database users** just because they are Windows login names.

You can check how many database users exist and reset a password, but first you need to connect as an administrator such as `SYS` or `SYSTEM`.

## **1. Connect as SYSDBA (Windows)**

Open **Command Prompt** and run:

```
sqlplus / as sysdba
```

This uses Windows authentication. It may work without asking for a password if your Windows account has the required Oracle administrator privileges (typically membership in `ORA_DBA`).

If it connects, you should see:

```
SQL>
```

If it fails, tell me the exact error.

## **2. Find how many Oracle users exist**

At the `SQL>` prompt, run:

```
SELECT COUNT(*) AS total_users
FROM dba_users;
```

To list the usernames:

```
SELECT username, account_status
FROM dba_users
ORDER BY username;
```

This shows database accounts and whether they are open, locked, or expired. It does not show passwords; Oracle stores password verifiers, not readable passwords.

## **3. Check which database or PDB you are connected to**

Run:

```
SHOW CON_NAME;
SHOW PDBS;
```

If your application user is in `FREEPDB1`, switch into that PDB:

```
ALTER SESSION SET CONTAINER = FREEPDB1;
```

Then list users in that PDB:

```
SELECT username, account_status
FROM dba_users
ORDER BY username;
```

## **4. Reset the password for&#x20;**`GOPI`

First check whether the account exists:

```
SELECT username, account_status
FROM dba_users
WHERE username = 'GOPI';
```

If it exists, reset its password and unlock it:

```
ALTER USER GOPI IDENTIFIED BY "NewPass#2026";
ALTER USER GOPI ACCOUNT UNLOCK;
```

Replace `NewPass#2026` with a strong password of your choice.

If `GOPI` does not appear, that user does not exist in the current database/PDB. You can create it:

```
CREATE USER GOPI IDENTIFIED BY "NewPass#2026";

GRANT CREATE SESSION, CREATE TABLE TO GOPI;

ALTER USER GOPI QUOTA UNLIMITED ON USERS;
```

## **5. Test the login**

Exit SQL\*Plus:

```
EXIT;
```

Then connect to the PDB:

```
sqlplus GOPI@localhost:1521/FREEPDB1
```

Enter the new password when prompted.

**Important:** `FREEPDB1` is an example service name. If your database uses a different PDB/service name, use the one shown by `SHOW PDBS` and your listener configuration.

## **Please run these commands first**

Try this in Command Prompt:

```
sqlplus / as sysdba
```

If it connects, run:

```
SHOW CON_NAME;
SHOW PDBS;

SELECT username, account_status
FROM dba_users
ORDER BY username;
```

Send me the output. I can then tell you exactly which user accounts exist and which commands to use to reset `GOPI` without changing the wrong database.
