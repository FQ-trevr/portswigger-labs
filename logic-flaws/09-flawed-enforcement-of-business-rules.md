# Lab: Flawed enforcement of business rules

Login using the provided creds and notice the banner for the coupon code, `NEWCUST5`, which gives a $5 discount on a purchase.

Scroll to the bottom of the page to see that there is a newsletter signup. Enter a random email. The site responds with a notification for another coupon code, `SIGNUP30`, which gives a 30% discount.

Add the jacket to the cart and go to the cart page. Apply the coupon codes. Try adding them again to see that if the same code is used twice consecutively, the site responds with an error indicating the code has already been used. However, applying the codes in an alternating pattern results in exploitation of a logic flaw, allowing multiple discounts to be applied more than once.

Add the codes until the cart total is below the available store credit amount. Complete the purchase to complete the lab.