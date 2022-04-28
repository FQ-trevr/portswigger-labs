# Lab: DOM XSS using web messages and a JavaScript URL

Inspect the page source and notice that there is an `addEventListener()` call that listens for a web message, then parses a url from the function parameters via indexing `'http(s):'`.

Store the following exploit code on the exploit server and deliver it to complete the lab:

`<iframe src="https://ac601fbb1f539c12c0e1574a003000ad.web-security-academy.net/" onload="this.contentWindow.postMessage('javascript:print()//http:','*')">`

This script sends a web message containing an arbitrary JavaScript payload, along with the string `'http:'`. The second argument specifies that any targetOrigin is allowed for the web message. When the iframe loads, the postMessage() method sends the JavaScript payload to the main page. The event listener sees the `'http:'` string and proceeds to send the payload to the location.href sink, where the print() function is called.