# Lab: Multi-step process with no access control on one step

Login as administrator with the provided credentials and go to the admin panel to get familiar with the operation.

Turn on proxy and upgrade carlos. Inspect the requests to see that the last step contains the paremeters: `action=upgrade&confirmed=true&username=carlos`

Login with `wiener:peter` and replay the request, but with the session cookie replaced with the value of the current user and the username parameter as `wiener`. This results in upgrading the current user and completion of the lab.