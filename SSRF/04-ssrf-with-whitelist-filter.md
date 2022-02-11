# Lab: SSRF with whitelist-based input filter

Navigate to a product page and turn on the proxy. Check the stock for the product and intercept the request. Send it to the repeater and change the `stockApi` URL to `http://localhost/`. This returns the message, "External stock check host must be stock.weliketoshop.net"

Send a request with the URL `http://username@stock.weliketoshop.net/` to see that the parser is processing credentials. Add `#` to see that the request is rejected. Double-url-encode `#` to `%2523` and see that a 500 error is returned.

Put this all together to get the url to delete carlos: `http://localhost%2523@stock.weliketoshop.net/admin/delete?username=carlos`