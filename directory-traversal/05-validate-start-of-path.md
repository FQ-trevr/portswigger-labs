# Lab: File path traversal, validation of start of path

Intercept a GET request for one of the product images. Change `filename=<image-id>` to `filename=/var/www/images/../../../etc/passwd`.

This complies with the app requirement for filenames to start with the expected base folder while still allowing traversal.

Check the response to see that the file is returned.