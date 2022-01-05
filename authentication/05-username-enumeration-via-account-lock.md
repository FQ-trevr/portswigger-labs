# Lab: Username enumeration via account lock

Navigate to the login page and try a random credential pair to see that the response includes an error message: `Invalid username or password`

Send the request to the intruder:
1. Set the attack type to cluster bomb
2. Set the payload to the usernames list and 5 or 6 random passwords
3. Set the options to grep match for the error message `Invalid username or password`

Running the attack shows that for most usernames the error message is the grep match message, but for the username `adm` it is `You have made too many incorrect login attempts`, indicating a logic flaw and enumerating a valid username.

Modify the intruder attack to use the discovered username and set the password payload to use the full list of passwords. Set to sniper attack type and set the grep match to find the account lockout message. Running the attack again shows that most passwords result in the account lockout message or the invalid creds error message. However, another logic flaw exists for the case of the valid password, which has no error message: `computer`

Login with `adm:computer`