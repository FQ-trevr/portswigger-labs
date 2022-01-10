# Lab: File path traversal, traversal sequences stripped non-recursively

Intercept a GET request for one of the product images. Change `filename=<image-id>` to `filename=....//....//....//etc/passwd`.

Check the response to see that the file is returned.