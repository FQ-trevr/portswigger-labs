# Lab: SQL injection UNION attack, retrieving data from other tables

Knowing the number of columns and data types matches between the `users` table and the `Accessories` table, modify the payload to include a union for the relevant data:

`'+UNION+SELECT+username,+password+FROM+users--`