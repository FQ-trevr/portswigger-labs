# Lab: Username enumeration via response timing

Check for response time differences by submitting the known valid username with different password lengths. Note that longer passwords take longer to return a response.

Send the request to the intruder and add the X-Forwarded-For header to circumvent the ip-based brute-force protection mechanism. Set the intruder attack type to pitchfork. Configure the attack to use integers as the payload for the X-Forwarded-For ip variable and to use the username list as the username variable. Set the password to be long enough to show an obvious difference in processing time.

Running the attack shows one username taking much longer than the others. Modify the intruder settings to use this username and swap out the variable for the password field, using the passwords list as the payload. Find the response that returns 302 - Found. Login with the discovered credentials.