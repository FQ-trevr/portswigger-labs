# Lab: Reflected XSS into a JavaScript string with angle brackets and double quotes HTML-encoded and single quotes escaped

Search for `';alert(document.domain)//` and see that it is escaped as `'\';alert(document.domain)//'`

Add a leading slash to escape the escape character and trigger an alert: `\';alert(document.domain)//`