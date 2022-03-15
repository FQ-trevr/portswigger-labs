# Lab: DOM XSS in innerHTML sink using source location.search

Perform a search and inspect the page to see that location.search is used to provide data to an innerHTML assignment.

Use the following payload to trigger the XSS and complete the lab: `<img src=1 onerror=alert(document.domain)>`

The value of the src attribute is invalid and throws an error. This triggers the onerror event handler, which then calls the alert() function. As a result, the payload is executed whenever the user's browser attempts to load the page containing the malicious payload.