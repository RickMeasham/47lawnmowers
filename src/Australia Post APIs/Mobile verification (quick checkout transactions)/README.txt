Who uses this API?
Example: You want to share your lawnmower with your trusted local community. You have built an app or web page for that. An Australia Post registered “customer” who needs that lawnmower gives you his/her mobile number to verify their identity. You use this API to send a code to that mobile number. The customer gives you that code that you then enter in your app and Australia Post sends you the residential address registered for that mobile number. You can then crosscheck their identity claims.
 
To use the API:
1) You can use swagger to get the sample addresses: 
http://192.168.210.14:8080/checkoutapi/v1/_admin/swagger/index.html#!/checkout-controller/validateCheckout

2) Sample address are there for these codes:
validationCode - 111111
validationCode - 222222
validationCode - 333333

To use the UI component:
Enter any mobile number and any of the 3 validation codes to get the customers residential address.