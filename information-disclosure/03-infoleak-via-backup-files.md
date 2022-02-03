# Lab: Source code disclosure via backup files

Open the Target tab in Burp and right-click the lab domain. Select Engagement Tools > Discover Content, then start the scan.

After running for a while, notice that there is a `/backup` path. Open this in the browser to see a page linking to `ProductTemplate.java.bak`

Click on the file and see that there is a database connection method containing the database password. Submit it to complete the lab.

The path can also be discovered by browsing to `/robots.txt`, which is a bit easier.