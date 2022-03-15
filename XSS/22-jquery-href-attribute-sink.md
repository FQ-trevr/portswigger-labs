# Lab: DOM XSS in jQuery anchor href attribute sink using location.search source

Go to the Submit Feedback page and inspect it. Notice that the url query parameter for returnPath is populated in the "back" link. Change the path to a random string and reload the page to validate this.

Set the returnPath to `javascript:alert(document.cookie)` to solve the lab.