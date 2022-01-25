# Lab: Authentication bypass via flawed state machine

Notice that the site has an `/admin` path that is only accessible when logged in as an administrator.

Login using the provided credentials. Notice that the login flow has a `role-selector` page.

Intercept the post request and change the role selected to `administrator` - this doesn't work.

Logout and log back in, allowing the `POST /login` request to be forwarded, but dropping the `GET /role-selector` request. An error is thrown. Navigate back to the site home page and see that the role has defaulted to administrator, as there is now a link for `Admin Panel`.

Delete carlos to finish the lab.