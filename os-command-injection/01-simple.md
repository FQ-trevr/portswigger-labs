# Lab: OS command injection, simple case

Intercept a request for checking product stock.

Modify the `storeID` parameter to be `1|whoami` and see that the current user is returned.