# Lab: Reflected XSS into HTML context with most tags and attributes blocked

Try searching for `<img src=1 onerror=print()>` and observe that the request is blocked.

Intercept a search request, send it to intruder, clear out the payload positions, and replace the search term with `<§§>`

Copy the tags list from https://portswigger.net/web-security/cross-site-scripting/cheat-sheet

Paste the list in as the payload list for intruder and run the attack. Notice that only the <body> tag returns a 200, with all others being blocked.

Repeat the attack with the search term set to `<body%20§§=1>`, using the events list from the above url as the payload list. Notice that only the "onresize" payload returns a 200.

This tag/event combination allows the following payload to be constructed: `<body onresize="print()">`

Open the exploit server for the lab and paste in the following: `<iframe src="https://lab-subdomain.web-security-academy.net/?search=%22%3E%3Cbody%20onresize=print()%3E" onload=this.style.width='100px'>`

Save it and deliver/email the link to the victim to solve the lab.

---

The iframe embeds the target page into the html of the exploit page.

The onresize attribute is an event that executes the javascript when the window is resized.

The onload event triggers the onresize event when the page is loaded.

Together, this means that when the victim clicks the exploit link, the XSS will be triggered. Instead of a print() action, malicious code could be inserted to compromise cookies or other sensitive values.

The labs provide a guarantee that the target user will click any link that is sent, so the last step is simplified.