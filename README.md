This application is the server part of a OAuth2 application using spring boo2.  
The server will generally be used  to create application access tokens.  
During the access tokens generation process, the server will use information stored inside OAUTH_CLIENT_DETAILS table.  
The server will also make use of APPUSER table to verify that BASIC authentication requirements are satisfied while request for a access token by a client.  

There is a user creation and client registration process involved in this flow which is not covered in these application.   
These two process are executed with the SQL commands which are provided in create.sql and insert.sql files.   

There is a JWT key pare provided in the application. The server application used the private JWT key to encrypt the access token.  The public part of the key should be with the application who wants to validate the access token and make use of it.  The keys are generated using java keytool utility with RAS256 algorithms.  Once keys are generated they are migrated to PKCS12 format using the keyltool utility.

Install Derby database locally and run as a network server.

Run the application and use postman client to request the application for a access token. On the Authorization header use username "USER_CLIENT_APP" and password as "PASSWORD".  On the body, use grant_type as password, username as admin and password as "password"

