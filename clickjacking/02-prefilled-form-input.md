# Lab: Clickjacking with form input data prefilled from a URL parameter

Login with the provided creds. Go to the account page with the url parameter to set the email included: `https://<lab-domain>.web-security-academy.net/my-account?email=<attacker-email>`

Open Burp and from the menu, select Clickbandit. Copy the clickbandit script and in the browser open devtools. Paste the script into the console and run it. Start and click on the update email button, then finish, toggle opacity, and download.

Paste the resulting html into the exploit body and deliver it to the victim to complete the lab.