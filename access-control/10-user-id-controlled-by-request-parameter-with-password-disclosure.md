# Lab: User ID controlled by request parameter with password disclosure

Login with the provided creds. Navigate to `/my-account?id=administrator` and see that horizontal privilege escalation is available and that the user's password is pre-filled as a masked value. Inspect the page response to see that the value is exposed in the html.

Logout and log back in as administrator using the discovered password. Delete carlos to finish the lab.