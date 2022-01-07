# Lab: 2FA bypass using a brute-force attack

Login with the known creds and try a random 2fa code. Notice that after two attempts the application logs the user out.

Create a macro to automate the initial login:
1. under Project Options > Sessions, select Session Handling Rules and add a rule
2. change the URL scope to include all URLs
3. under Details, add a Rule Action with the Run Macro option
4. filter for the base domain and select the following to record the macro:
    ```
    GET /login
    POST /login
    GET /login2
    ```
5. test to verify that the last response contains the 2fa parameter
6. send the POST /login2 to the intruder and select the 2fa parameter as the variable
7. set the attack to use number payload 1000-9999 with step of 1 (leaves out 0000, but that's probably preferable to running 999 known invalid codes)
8. set the resource pool to have max concurrent requests = 1
9. start the attack and monitor for a 302 response

Once found, load the response in the browser to login as carlos.