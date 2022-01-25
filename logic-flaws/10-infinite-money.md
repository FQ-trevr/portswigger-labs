# Lab: Infinite money logic flaw

Login using the provided credentials. Notice that there is a gift card entry field on the account page.

Notice that the newsletter signup at the bottom of the page again gives the 30% discount code `SIGNUP30`.

On the products page, see that there is a gift card item for $10. Turn on the proxy. Add it to the cart and apply the coupon to purchase it for $7.

On the next page the gift card code is displayed. Copy it and go to the account page to enter it into the redemption field. See that the available store credit has increased to $3 over what was initially available.

In Burp, go to Go to "Project options" > "Sessions"

Create a macro to automate the gift card flow:
1. under Project Options > Sessions, select Session Handling Rules and add a rule
2. change the URL scope to include all URLs
3. under Details, add a Rule Action with the Run Macro option
4. select the following to record the macro:
    ```
    POST /cart
    POST /cart/coupon
    POST /cart/checkout
    GET /cart/order-confirmation?order-confirmed=true
    POST /gift-card
    ```
5. click Configure Item for the GET request and add a custom parameter
6. name the parameter "gift-card" and highlight the code at the bottom of the response
7. click the final POST request and again configure the item
8. under Parameter Handling, specify that response 4 should be used for the gift-card parameter
9. test the macro to verify that the last response contains the gift card code from the 4th response
10. send the GET /my-account request to the intruder and clear the parameters
11. set the attack to use null payload with a count of ~415
12. set the resource pool to have max concurrent requests = 1
13. start the attack and wait for the available store credit to reach the necessary threshold

Add the jacket to the cart and complete the purchase to finish the lab.