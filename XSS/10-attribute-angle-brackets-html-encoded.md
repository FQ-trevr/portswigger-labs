# Lab: Reflected XSS into attribute with angle brackets HTML-encoded

Search for `" autofocus onfocus=alert(document.domain) x="` to solve the lab.

This creates an onfocus event that will execute JavaScript when the element receives the focus. It also adds the autofocus attribute to try to trigger the onfocus event automatically without any user interaction. Finally, it adds x=" to gracefully repair the following markup.