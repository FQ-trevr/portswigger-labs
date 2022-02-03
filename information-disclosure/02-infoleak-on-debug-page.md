# Lab: Information disclosure on debug page

In Burp, open the Target tab. Right click on the lab domain and select Engagement Tools > Find Comments.

Inspect the comments found to see that there are many entries for a link to "Debug" with the path `/cgi-bin/phpinfo.php`

Navigate to this path and search for "SECRET_KEY" to find the lab solution.