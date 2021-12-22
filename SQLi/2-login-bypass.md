# Lab: SQL injection vulnerability allowing login bypass

modify the username parameter to be `administrator'--`

Password can be anything or blank because the -- chars place it in comments, resulting in the administrator account being returned without evaluating the credential.