# Lab: Insufficient workflow validation

Login and add an item to the cart. Turn on the proxy and then complete the purchase.

Notice that the `POST /cart/checkout` request results in a redirect to `GET /cart/order-confirmation?order-confirmation=true`. Send this request to the repeater.

Add the jacket to the cart and then resend the order confirmation request to solve the lab.