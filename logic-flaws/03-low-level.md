# Lab: Low-level logic flaw

Intercept a POST /cart request for the jacket being added. Modify the quantity payload to be 99 (max allowed is 2 digits) and send the request to the intruder.

Clear the payload positions, set payload to be "null payloads" and "continue indefinitely"

Run the attack and refresh the cart periodically. Notice that the cart total increases steadily, but then sharply becomes negative before counting back up. This behavior loops.

Stop the attack and clear the cart by removing an item and modifying the decrement quantity to be the total number of items in the cart.

Create the same intruder attack, but set it to use 323 payloads (still using 99 jackets per request). Set the max concurrent requests to 1 and run the attack. When it finishes, send an additional request for 47 jackets. This results in the cart total being -$1221.96

Add some additional items such that the cart total is between 0 and 100. Complete the purchase to finish the lab.

-------------------

There isn't an adequate explanation for the determination of the max value as noted in the lab solution (2,147,483,647 - corresponding to some C-family languages). While a real-world attack wouldn't necessarily provide any information about the backend language, the process described in the solution doesn't allow for observation of the value of the loop threshold without painstaking effort. There should be a better explanation of the method used for reaching the necessary conclusions.