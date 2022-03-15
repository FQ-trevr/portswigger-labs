# Lab: Reflected XSS with AngularJS sandbox escape without strings

A successful exploit needs to use a toString() to create a string without quotes. Next, the String prototype should be used to overwrite the charAt function for every string to break the sandbox. Next, an array can be passed into the orderBy filter, then the argument can be set again using toString(). This will create a string and the String constructor property. Last, use the fromCharCode method to create the payload using conversion of character codes into the string, which is `x=alert(1)`. The charAt function has been overwritten, so AngularJS will allow the code.

The complete exploit is: `https://ac711f5f1ef5c34cc0e70e5f0013007e.web-security-academy.net/?search=1&toString().constructor.prototype.charAt%3d[].join;[1]|orderBy:toString().constructor.fromCharCode(120,61,97,108,101,114,116,40,49,41)=1`
