# Lab: Password reset poisoning via middleware

Navigate to the password reset request page and intercept the `POST` request. See that the X-Forwarded-Host header is supported.

Initiate a password reset for the target account and add the header with the value of the exploit server. Open the exploit server access log and find the `GET /forgot-password` request. Copy the token from the query parameter.

Submit a reset request for the wiener/peter user and click the emailed link. Enter a new password and intercept the post request. Replace the password reset token with the stolen token. Submit the request and login as carlos.