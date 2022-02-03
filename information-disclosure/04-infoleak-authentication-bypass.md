# Lab: Authentication bypass via information disclosure

Turn on proxy and navigate to `/admin` to see that it is blocked. Reload and intercept the `GET` request. Change the method to `TRACE` and inspect the resulting response.

Notice the `X-Custom-IP-Authorization: <your-ip>` header.

In Proxy > Options, Add a rule to "Match and Replace" with the condition blank, but with `X-Custom-IP-Authorization: 127.0.0.1` as the Replace field. This will cause Burp to add the header to all requests and will indicate to the server that the request is originating from localhost.

Browse back to `/admin` and see that it is unblocked. Delete carlos to complete the lab.