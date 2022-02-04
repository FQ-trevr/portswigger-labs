# Lab: Method-based access control can be circumvented

Login with the admin creds and go to the admin panel. Upgrade and downgrade carlos to see what the requests look like. Login with `wiener:peter` and attempt to replay the requests with the session cookie replaced by the value for the current user. This results in the message "unauthorized."

Try changing the request method to `POSTX` and see that the message is now "Missing Parameter 'username'"

Right-click the request and choose "Change request method" to use `GET` and modify to the current username. Forward the request to upgrade the user to admin and complete the lab.