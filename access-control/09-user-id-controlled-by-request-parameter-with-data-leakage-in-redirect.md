# Lab: User ID controlled by request parameter with data leakage in redirect

Login with the provided creds. Turn on proxy and go to `/my-account?id=carlos` and see that the site redirects to the login page. Inspect the intercepted request and see that the account page for carlos was actually returned, but not displayed. Submit the API key to complete the lab.