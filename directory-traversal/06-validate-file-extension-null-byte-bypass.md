# Lab: File path traversal, validation of file extension with null byte bypass

Intercept a GET request for one of the product images. Change `filename=<image-id>` to `filename=../../../etc/passwd%00.png`.

This complies with the app requirement for filenames to end with the expected extension while still allowing traversal.

Check the response to see that the file is returned.