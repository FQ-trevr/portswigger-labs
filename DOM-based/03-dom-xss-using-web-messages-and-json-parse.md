# Lab: DOM XSS using web messages and JSON.parse

Inspect the page source to find that there is an event listener expecting a string that is parsed using JSON.parse(). The script expects a type property and the load-channel switch case changes the iframe src attribute.

Using this information, the following exploit can be constructed:

`<iframe src=https://acd11f301e8b641ec067664800480062.web-security-academy.net/ onload='this.contentWindow.postMessage("{\"type\":\"load-channel\",\"url\":\"javascript:print()\"}","*")'>`

This triggers the load-channel case and executes the javascript call through the url sink of the iframe src attribute.

As the second argument specifies that any targetOrigin is allowed for the web message, and the event handler does not contain any form of origin check, the payload is set as the src of the ACMEplayer.element iframe. The print() function is called when the victim loads the page in their browser.