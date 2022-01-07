# Lab: Password brute-force via password change

Login as the known user and navigate to the password change page. Do some testing to see that if an incorrect current password is entered the user is locked out, but if the correct password is entered and the new password fields don't match, the message `New passwords do not match` is displayed instead.

Submit the password change form and intercept the `POST` request. Send to intruder and change the parameters to use the target username and two different new passwords. Set the payload to use the passwords list and fill the current password field as the variable. Also set grep match to find the error message.

Start the attack and find the response with the grep match to discover the target user's current password. Login as carlos.