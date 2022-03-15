# Lab: Stored DOM XSS

Inspect the blog post page to see that there is a function to escape html:
```
function escapeHTML(html) {
    return html.replace('<', '&lt;').replace('>', '&gt;');
}
```

Use `<><img src=1 onerror=alert(1)>` as the Name field to submit a comment in order to exploit the vulnerability.

This works because the function only replaces the first set of brackets with encoded brackets, leaving the rest to be executed.