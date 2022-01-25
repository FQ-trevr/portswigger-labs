# Lab: Weak isolation on dual-use endpoint

Login with the provided credentials. On the account page, notice that there is a password reset form. The username field is pre-filled, but can be edited. This is a nice hint, as the username clearly gets passed as a parameter. However, even if it wasn't editable in the page there could have been a way to modify it before sending the request, depending on the implementation.

Navigate to the `/admin` path and see the error message noting that only the user `administrator` can access the page.

On the account page, change the username to `administrator` and fill in some values for the current password and new password fields. Intercept the request and remove the following part of the parameters: `&current-password=<whatever-was-entered>`

Send the request and see that the password change was successful.

Logout and log back in as administrator with the newly set password. Delete carlos to finish the lab.