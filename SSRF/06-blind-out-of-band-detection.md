# Lab: Blind SSRF with out-of-band detection

Open a product page with the proxy turned on to intercept the request. Open Burp Collaborator and copy a payload. Replace the `Referrer` header in the request to use the payload similar to `https://<random-string>.burpcollaborator.net`

Forward the request and see that DNS and HTTP requests to the collaborator server were triggered, solving the lab.