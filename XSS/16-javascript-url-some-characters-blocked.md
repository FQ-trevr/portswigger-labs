# Lab: Reflected XSS in a JavaScript URL with some characters blocked

Go to the path `/post?postId=5&'},x=x=>{throw/**/onerror=alert,1337},toString=x,window+'',{x:'`

The exploit uses exception handling to call the alert function with arguments. The throw statement is used, separated with a blank comment in order to get round the no spaces restriction. The alert function is assigned to the onerror exception handler.

As throw is a statement, it cannot be used as an expression. Instead, arrow functions can be used to create a block so that the throw statement can be used. To call the function, assign it to the toString property of window and trigger this by forcing a string conversion on window.