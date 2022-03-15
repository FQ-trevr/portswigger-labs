# Lab: DOM XSS in document.write sink using source location.search inside a select element

Inspect a product page and notice that the javascript accepts a `storeId` parameter from the `location.search` source, which is used to update the stock checker options list. Try adding a storeId param to the path to validate this: `/product?productId=1&storeId=asdf`

Repeat this with an XSS payload to complete the lab: `/product?productId=1&storeId="></select><img%20src=1%20onerror=alert(1)>`