# Lab: Basic SSRF against the local server

Navigate to a product page and turn on the proxy. Check the stock for the product and intercept the request.

Change the `stockApi` URL to `http://localhost/admin` and forward the request to see that the admin panel is returned, listing users with delete links.

Try to delete carlos and see that the request is to `GET /admin/delete?username=carlos`

Drop the request and repeat the product stock check, but this time modify the URL to `stockApi=http://localhost/admin/delete?username=carlos` to delete carlos.