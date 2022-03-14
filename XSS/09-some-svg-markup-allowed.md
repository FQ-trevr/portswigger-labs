# Lab: Reflected XSS with some SVG markup allowed

This is basically the same as lab 6 (Reflected XSS into HTML context with most tags and attributes blocked). There is nothing new here, just different tags and context.

The search payload to solve the lab is `"><svg><animatetransform onbegin=alert(1)>`