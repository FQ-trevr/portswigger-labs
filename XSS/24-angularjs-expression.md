# Lab: DOM XSS in AngularJS expression with angle brackets and double quotes HTML-encoded

Perform a search and inspect the page to see that the string is placed in an ng-app directive.

Search for `{{$on.constructor('alert(1)')()}}` to trigger the XSS vulnerability.