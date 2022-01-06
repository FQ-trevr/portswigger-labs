# Lab: 2FA broken logic

Navigate to the login page and enter the valid credentials. Intercept the request and send it to the repeater.

Change the `verify ` parameter to `carlos` and send the request to generate a verification token for the target user.

Enter a random verification code for the valid user and intercept the request. Send it to the intruder and again change the `verify ` parameter to `carlos`.

Set the mfa-code to a variable. Set the attack payload to use numbers 1000-9999 with a step of 1 to brute-force the verification code for the target user. Start the attack and set to filter out 2xx status codes from the results. When a 302 is discovered, the valid verification code has been found.

Load the response in the browser to login as carlos.