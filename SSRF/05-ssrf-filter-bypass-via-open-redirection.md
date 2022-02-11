# Lab: SSRF with filter bypass via open redirection vulnerability

Navigate to a product page and turn on the proxy. Check the stock for the product and intercept the request. Try changing the stockApi param to see that it doesn't directly allow exploitation of SSRF.

Look around the site and find that the product page "Next product" link request contains a path parameter. This can be used for redirection.

Using the product stock checking functionality, change the stockApi URL to `/product/nextProduct?path=http://192.168.0.12:8080/admin` and send the request to see that the admin interface is returned, indicating successful exploitation of an open redirect vulnerability.

Submit another request with `stockApi=/product/nextProduct?path=http://192.168.0.12:8080/admin/delete?username=carlos` to delete carlos.