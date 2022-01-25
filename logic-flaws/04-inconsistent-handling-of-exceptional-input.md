# Lab: Inconsistent handling of exceptional input

Proxy traffic through Burp and open the "Target" tab. Under "Site Map", right-click the lab domain and select "Engagement Tools" > "Discover content".

Click "Session is not Running" and wait for the mapping to complete. Notice that there is a `/admin` path. Try navigating to it to see that the error message returned indicates that only `DontWannaCry` users have access.

Notice that the account registration page has a message telling `DontWannaCry` employees to use an `@dontwannacry.com` email address to register.

Open the lab email client and copy the unique id in the domain of the server (`@<email-id>.web-security-academy.net`). Register an account with a long string of several hundred characters (`<long-string>@<email-id>.web-security-academy.net`). Click the received registration link, login, and navigate to the account page. Notice that the email address displayed has been truncated to 255 characters.

Logout and register a new account with an email address like the following:

`aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa@dontwannacry.com.<email-id>.web-security-academy.net`

This contains the `@dontwannacry.com` email domain at exactly 255 characters so that the truncation will result in only the target domain being retained at the end of the address. After confirming registration and logging in, go to the `/admin` page and see that it loads successfully. Delete the user "carlos" to finish the lab.