# Lab: Inconsistent security controls

Based on the last lab, assume that the admin interface is at the `/admin` path (or discover it using the same method). This is the case and the same error is displayed noting that only `DontWannaCry` users can view the page.

Create a user using the email provided by the exploit server. Click the received link to complete registration.

Now go to the account page and change the email to `<something>@dontwannacry.com`

This is successful. Go to the admin page and delete carlos to finish the lab.