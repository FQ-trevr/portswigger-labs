# Lab: Reflected DOM XSS

Turn on the proxy and perform a search. Inspect the intercepted response to see that the search query string is reflected in the json response. Open DevTools and find searchResults.js. Notice that the json is used in an eval() function call.

Experiment with different searches to determine that the json response doesn't escape backslashes, but does escape double quotes. Use the search `\"-alert(1)}//` to exploit this and trigger the XSS. This causes the quote to be escaped, but the added backslash is cancelled by the leading backslash, resulting in the quote being unescaped.

From the lab explanation:

An arithmetic operator (in this case the subtraction operator) is then used to separate the expressions before the alert() function is called. Finally, a closing curly bracket and two forward slashes close the JSON object early and comment out what would have been the rest of the object. As a result, the response is generated as follows: `{"searchTerm":"\\"-alert(1)}//", "results":[]}`