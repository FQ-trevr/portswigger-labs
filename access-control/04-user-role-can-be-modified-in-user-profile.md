# Lab: User role can be modified in user profile

Login with the provided creds.

Mess around and notice nothing of value.

Decide that the email change functionality must be the key.

Submit an email change and intercept the request. See that there is a block in the POST request that can be modified according to the lab instructions:
```
{
    "email":"<whatever>@<something>.com"
}
```

```
{
    "email":"<whatever>@<something>.com",
    "roleid":2
}
```

Forward the request and see the link for the Admin Panel is now available. Delete carlos because he is the worst.