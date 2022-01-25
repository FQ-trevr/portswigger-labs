# Lab: Authentication bypass via encryption oracle

Log in and check the "stay logged in" option.

Go to a post and add a comment. Play around with the form and notice that if an invalid email is entered, an error message is displayed: `Invalid email address: your-invalid-email`

Inspect the `GET /post?postId=n` request resulting from the `POST /post/comment/` request and see that the notification cookie is an encrypted value. This is probably the encrypted error message displayed on the resulting page.

Send both requests to the repeater. The POST request encrypts data via the resulting Set-Cookie header, while the GET request decrypts it and reflects it in the error message.

Copy the `stay-logged-in` cookie and paste it into the `notification` cookie. Send the request to see that the response contains the following: `wiener:1643146828463`

This appears to indicate that the `stay-logged-in` cookie has the format `username:timestamp`, so modifying it to be `administrator:1643146828463` will probably allow bypassing the authentication mechanism.

To do this, first encrypt the desired cookie (`administrator:1643146828463`) using the POST request in repeater. If the resulting cookie is decrypted, it results in the error message with the prefix "Invalid email address: ", which is problematic. Using this cookie would not decrypt to the proper result for bypassing authentication.

Instead, the prefix needs to be removed. Send the cookie to the decoder. URL-decode and then Base64-decode. In hex mode, delete the first 23 bytes.

**This step had me stuck for a while because there is a weird behavior in selecting bytes. If byte 23 is selected and then shift-click is used to select back to byte 1, only bytes 1-22 are selected. I thought I was selecting all 23, so everything after this was not working and I couldn't figure out why.**

Re-encode the data and decrypt it using the `notification` cookie of the GET request. The error message displayed indicates that a block encryption method is used, so the input length is required to be a multiple of 16.

Go back to the repeater and modify the POST request to use `xxxxxxxxxadministrator:1643146828463` as the email. The `x` characters function as padding to comply with the block encryption requirements.

Send the resulting cookie to the decoder and repeat the previous steps, but this time delete the first 32 bytes.

Decrypt the resulting cookie to verify that the result is `administrator:1643146828463`

Go into the proxy history to find the `GET /` request. Send it to the repeater. Paste the cookie into the `stay-logged-in` field and remove the session cookie. Send the request, load the response in the browser, and see that the logged in session is now for the administrator.

Navigate to `/admin` and delete carlos to finish the lab.