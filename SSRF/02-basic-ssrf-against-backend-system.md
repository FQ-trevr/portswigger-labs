# Lab: Basic SSRF against another back-end system

Navigate to a product page and turn on the proxy. Check the stock for the product and intercept the request. Send it to the intruder and change the `stockApi` URL to `http://192.168.0.§x§:8080/admin`, with `§x§` set as the payload position. Set the payload to use numbers from 0-255 with a step of 1. Run the attack and look for a 200 response. In my case, the 200 was found for x=132.

Repeat the product stock check, but this time modify the URL to `stockApi=http://192.168.0.132:8080/admin/delete?username=carlos` to delete carlos.