# Lab: DOM XSS using web messages

Inspect the page source and notice that there is an `addEventListener()` call that listens for a web message.

Store the following exploit code on the exploit server and deliver it to complete the lab:

`<iframe src="https://ac161f0a1e0b4e73c06d1a5500670035.web-security-academy.net/" onload="this.contentWindow.postMessage('<img src=1 onerror=print()>','*')">`

When the iframe loads, the postMessage() method sends a web message to the home page. The event listener, which is intended to serve ads, takes the content of the web message and inserts it into the div with the ID ads. However, in this case it inserts an img tag, which contains an invalid src attribute. This throws an error, which causes the onerror event handler to execute the payload.