# Lab: Broken brute-force protection, IP block

Attempt login using the valid credentials provided to observe behavior. Try using invalid creds as well. Notice that the login form is locked after 3 unsuccessful attempts, but that logging in successfully resets the count.

Send the request to the intruder and set the intruder attack type to pitchfork. There is probably also a way to do this using the cluster bomb attack type that would be slightly less work, as only two usernames would be needed in the username payload list, but I tried this and the attack order was affected in a way that caused lockouts. Perhaps setting the threads to 1 would do it, but this would be very slow.

Using pitchfork, configure the attack to use an alternating list of `wiener/carlos` as the payload for the username variable. Edit the password list to use an alternating list of `peter/<bruteforce>`, where `<bruteforce>` is from the list of possible passwords.

Running the attack doesn't work because the concurrency results in some requests finishing before others, which causes invalid creds to be tried in succession. In the intruder options, set the resource pool to use 2 max concurrent requests. Filter out the 2xx responses from the results to see that only one password worked for the target: `carlos:austin`

Login with the discovered password.