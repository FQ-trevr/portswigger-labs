# Lab: URL-based access control can be circumvented

Navigate to `/admin` and see that there is an Access Denied message.

Intercept the request and change the URL request line to `/` and add the header `X-Original-URL: /admin`

Apparently, first adding the header `X-Original-URL: /invalid` indicates that the backend is processing the URL from the header because it returns "Not Found"

To delete carlos, add `?username=carlos` to the query string and add the header `X-Original-URL: /admin/delete`

-----

I feel that the explanation provided in the introductory documentation was insufficient for solving this lab. Without a deep background in web applications, it is difficult to see how someone could know to use `/` as the request URL and to use `/invalid` for validating backend processing.