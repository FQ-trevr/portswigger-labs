# Lab: Username enumeration via different responses

Put in a random username/password to see that the page displays "Invalid password"

Send login page to intruder and modify payload to use username list, configure grep match to check for the error message. Running the attack shows that the error is not returned for the username "appserver"

Switch out the payload for the passwords list and run the attack again using the discovered username, this time checking for the message "Incorrect password"

This shows that "soccer" is the password. Login successfully.