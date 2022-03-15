# Lab: Reflected XSS with AngularJS sandbox escape and CSP

Go to the exploit server and store the following code:
```
<script>
location='https://acc21fd61e1c9d14c17b898500a6004d.web-security-academy.net/?search=%3Cinput%20id=x%20ng-focus=$event.path|orderBy:%27(z=alert)(document.cookie)%27%3E#x';
</script>
```

Deliver it to complete the lab.

This uses the ng-focus event to bypass the CSP, as well as the variable referencing the event object ($event). The path property is specific to Chrome and contains an array of elements that triggers the event. The last element in the array contains the window object.

Normally, | is a bitwise or operation in JavaScript, but in AngularJS it indicates a filter operation, in this case the orderBy filter. The colon signifies an argument that is being sent to the filter. In the argument, instead of calling the alert function directly, it is assigned to the variable z. The function will only be called when the orderBy operation reaches the window object in the $event.path array. This means it can be called in the scope of the window without an explicit reference to the window object, effectively bypassing AngularJS's window check.