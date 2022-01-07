# Lab: Brute-forcing a stay-logged-in cookie

Login with the known valid creds, selecting the "stay logged in" option.

Inspect the stay-logged-in cookie to see that it is base64 encoded:

`d2llbmVyOjUxZGMzMGRkYzQ3M2Q0M2E2MDExZTllYmJhNmNhNzcw`

--> `wiener:51dc30ddc473d43a6011e9ebba6ca770`

Where `51dc30ddc473d43a6011e9ebba6ca770` is the MD5 hash of the password.

Logout and navigate back to the login page. Send the request to the intruder and set the variable to the position of the cookie. Set the payload to use the known password. Select the following payload options (in order):
1. Hash: MD5
2. Add prefix `wiener:`
3. Base64-encode

Start the attack and see that it is successful. The response has the "Update email" option, which can be used to check for success during the brute force.

Modify the attack to use the target username and list of passwords as the payload.

Find the response with the grep match and load it in the browser to complete the lab.