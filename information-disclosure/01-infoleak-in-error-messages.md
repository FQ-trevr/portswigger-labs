# Lab: Information disclosure in error messages

Turn on the proxy and click on a product. Intercept the request and change the `productId` parameter to a non-integer like 'a' before forwarding the request.

The response is a 500 error which includes the stack trace. The framework and version are also included: Apache Struts 2 2.3.31

Submit the solution to complete the lab.