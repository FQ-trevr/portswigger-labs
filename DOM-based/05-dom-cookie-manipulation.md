# Lab: DOM-based cookie manipulation

Inspect the page source to see that it uses a client-side cookie called `lastViewedProduct` with the value being the url of the product page last viewed.

Use the following exploit payload:

<iframe src="https://acd41f3e1edad436c08b3e59008900b2.web-security-academy.net/product?productId=1&'><script>print()</script>" onload="if(!window.x)this.src='https://acd41f3e1edad436c08b3e59008900b2.web-security-academy.net/';window.x=1;">

The original source of the iframe matches the URL of one of the product pages, except there is a JavaScript payload added to the end. When the iframe loads for the first time, the browser temporarily opens the malicious URL, which is then saved as the value of the lastViewedProduct cookie. The onload event handler ensures that the victim is then immediately redirected to the home page, unaware that this manipulation ever took place. While the victim's browser has the poisoned cookie saved, loading the home page will cause the payload to execute.