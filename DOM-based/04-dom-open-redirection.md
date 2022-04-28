# Lab: DOM-based open redirection

The blog post page contains the following link, which returns to the home page of the blog:

`<a href='#' onclick='returnURL' = /url=https?:\/\/.+)/.exec(location); if(returnUrl)location.href = returnUrl[1];else location.href = "/"'>Back to Blog</a>`

The url parameter contains an open redirection vulnerability that allows the "Back to Blog" link destination to be changed. To solve the lab, construct and visit the following URL:

`https://<lab-domain>.web-security-academy.net/post?postId=4&url=https://<exploit-domain>.web-security-academy.net/`