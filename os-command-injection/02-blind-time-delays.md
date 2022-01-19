# Lab: Blind OS command injection with time delays

Intercept the email feedback request and modify the email parameter to be `email=x||ping+-c+10+127.0.0.1||` to see that the delay is triggered.