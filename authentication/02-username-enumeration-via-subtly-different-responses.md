# Lab: Username enumeration via subtly different responses

Try logging in to see that the page returns "Invalid username or password." when invalid creds are given.

Send the request to the intruder. Configure payloads to use the username list and set the options to extract the error message.

Running the attack shows that one of the responses is slightly different. For the user "accounting" the error message is instead "Invalid username or password "

Try the discovered name with the payload swapped for the passwords list. Reviewing the results, there is one response with a 302 where the rest are 200. Try this password with the username to login.