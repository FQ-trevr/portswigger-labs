# Lab: File path traversal, traversal sequences blocked with absolute path bypass

Intercept a GET request for one of the product images. Change `filename=<image-id>` to `filename=/etc/passwd`.

Check the response to see that the file is returned.