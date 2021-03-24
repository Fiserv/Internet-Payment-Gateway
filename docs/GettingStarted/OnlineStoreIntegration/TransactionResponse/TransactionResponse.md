---
title: Transaction Response
author: steffen.dangel@firstdata.de
---

## Step 2: Receiving the Transaction Result

&nbsp;

### Response to Your Success and Failure URLs

When you have submitted your transaction request to our Gateway using a HTML form, the transaction result will be sent back to your Success and Failure URLs as hidden fields. You can define these URLs in the transaction request (see responseFailURL and responseSuccessURL parameters [here][1]). Alternatively you can define them once in the Customitzation section of our Virtual Terminal.

Please consider when integrating that new response parameters may be added from time to time in relation to product enhancements or new functionality.

Make sure to use the parameter ‘response_hash’ to recheck if the received transaction response has really been sent by First Data in order to protect you from fraudulent manipulations. The value is created with a SHA Hash using the following parameter string:

<pre>sharedsecret + approval_code + chargetotal + currency + txndatetime + storename
</pre>

The hash algorithm is the same as the one that you have set in the transaction request. Please note that have to store the ‘txndatetime’ in order to be able to calculate the hash.

&nbsp;

### Server-to-Server Notifications

In addition to that mechnism, the Gateway can send server-to-server notifications to a defined URL. This is especially useful to keep your systems in synch with the status of a transaction for payment methods where the status can change at a later point. To use this notification method, you can specify an URL in the Customisation section of the Virtual Terminal or submit the URL in the additional transaction parameter ‘transactionNotificationURL’.

Please note that:

  * The Transaction URL is sent as received therefore please don’t add additional escaping (e.g. using %2f for a Slash (/).
  * No SSL handshake, verification of SSL certificates will be done in this process.
  * The Notification URL needs to listen either on port 80 (http) or port 443 (https) – other ports are not supported.
  * The response hash parameter for validation (using the same algorithm that you have set in the transaction request) ‘notification_hash’ is calculated as follows:

<pre>chargetotal + sharedsecret + currency + txndatetime + storename + approval_code</pre>

  
Such notifications can also be set up for Recurring Payments that get automatically triggered by the gateway. Please contact your local support team to get a Shared Secret agreed for these notifications. You can configure your Recurring Transaction Notification URL in the Virtual Terminal (Customisation/ Store URL Settings). In case of the recurring transactions the hash parameter is calculated as follows:

<pre>chargetotal + rcpSharedSecret+ currency + txndatetime + storename + approval_code</pre>

&nbsp;

> [Most Common Response Codes][2]

> [Step 3: Completion When Goods Get Shipped][3]

 [1]: http://test-ndpfdc.pantheonsite.io/org/gateway/node/224
 [2]: http://test-ndpfdc.pantheonsite.io/org/gateway/node/154
 [3]: http://test-ndpfdc.pantheonsite.io/org/gateway/node/318
