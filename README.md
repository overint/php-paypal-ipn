# PHP-PayPal-IPN
PHP Class for verifying PayPal Instant Payment Notification (IPN) messages.  
Use the `PaypalIPN` class in your project to handle the encoding of POST data, post back to PayPal, and parsing of the response from PayPal.

Example Use Case
---------

    use PaypalIPN;
    
    $ipn = new PayPalIPN();
    $ipn->useSandbox();
    $verified = $ipn->verifyIPN();
    if ($verified){
    	//process IPN
    }
  
  Features
--------

* Switch between live and sandbox by  using the `useSandbox` function.
* Verifies an HTTP "200" response status code from the PayPal server.
* Throws various exceptions to differentiate between common errors in code or
  server configuration versus invalid IPN responses.


Getting Started
---------------

This code is intended for web developers. You should understand how the IPN
process works conceptually and you should understand when and why you would be
using IPN. Reading the [PayPal Instant Payment Notification Guide][1] is a good
place to start.

You should also have a [PayPal Sandbox Account][2] with a test buyer account and
a test seller account. When logged into your sandbox account there is an IPN
simulator under the 'Test Tools' menu which you can used to test your IPN 
listener.

[1]: https://developer.paypal.com/docs/classic/ipn/integration-guide/IPNIntro/
[2]: https://developer.paypal.com

Once you have your sandbox account setup, you simply create a PHP script that
will be your IPN listener. In that script, use the `PaypalIPN` class as shown
above in the example use case.
