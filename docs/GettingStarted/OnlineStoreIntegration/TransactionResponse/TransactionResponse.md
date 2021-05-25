### Transaction Response
---

## Step 2: Receiving the Transaction Result

&nbsp;

### Response to Your Success and Failure URLs

When you have submitted your transaction request to our Gateway using a HTML form, the transaction result will be sent back to your Success and Failure URLs as hidden fields. You can define these URLs in the transaction request (see responseFailURL and responseSuccessURL parameters [here][1]). Alternatively you can define them once in the Customitzation section of our Virtual Terminal.

Please consider, when integrating, that new response parameters may be added from time to time in relation to product enhancements or new functionality.

Make sure to use the parameter ‘response_hash’ to recheck if the received transaction response has really been sent by Fiserv in order to protect you from fraudulent manipulations. The value is created with a HMAC&nbsp;Hash using the following parameter string:

<pre><span><span><span lang="EN-US"><span>approval_code|chargetotal|currency|txndatetime|storename</span></span></span></span>
</pre>

<span lang="EN-US"><span>Shared secret (‘</span></span><span lang="EN-US"><span>sharedsecret</span></span><span lang="EN-US"><span>’) will be used as a key in HMAC to&nbsp;calculate&nbsp;the hash with the above hash string.</span></span>

The hash algorithm is the same as the one that you have set in the transaction request. Please note that you have to store the ‘txndatetime’ in order to be able to calculate the hash.

&nbsp;

### Server-to-Server Notifications

In addition to that mechanism, the Gateway can send server-to-server notifications to a defined URL. This is especially useful to keep your systems in synch with the status of a transaction for payment methods where the status can change at a later point. To use this notification method, you can specify an URL in the Customization section of the Virtual Terminal or submit the URL in the additional transaction parameter ‘transactionNotificationURL’.

Please note that:

  * The Transaction URL is sent as received therefore please don’t add additional escaping (e.g. using %2f for a Slash (/).
  * No SSL handshake, verification of SSL certificates will be done in this process.
  * The Notification URL needs to listen&nbsp;on port 443 (https) – other ports are not supported

The response hash parameter for validation (using the same algorithm that you have set in the transaction request) ‘notification_hash’ is calculated as follows:

<pre><span><span><span lang="EN-US"><span>chargetotal|currency|txndatetime|storename|approval_code</span></span></span></span></pre>

<span lang="EN-US"><span>Shared secret (‘</span></span><span lang="EN-US"><span>sharedsecret</span></span><span lang="EN-US"><span>’) will be used as a key in HMAC to&nbsp;calculate&nbsp;the hash with the above hash string.</span></span>

  
Such notifications can also be set up for Recurring Payments that get automatically triggered by the gateway. Please contact your local support team to get a Shared Secret agreed for these notifications. You can configure your Recurring Transaction Notification URL in the Virtual Terminal (Customization/ Store URL Settings). In case of recurring transactions the hash parameter is calculated as follows:

<pre><span><span><span lang="EN-US"><span>chargetotal|currency|txndatetime|storename|approval_code</span></span></span></span></pre>

<span><span><span lang="EN-US">Shared secret (‘</span><span lang="EN-US"><span>rcpSharedSecret</span></span><span lang="EN-US">’) will be used as a key in HMAC to calculate&nbsp;the hash with the above hash string.</span></span></span>

&nbsp;

### Response Details

> [Response Fields that will be sent to the defined URL][2]  
> [Response Codes][3]

> [Authorisation Platform Specific Response Codes][4]

&nbsp;

### Next Steps

> [Step 3: Completion When Goods Get Shipped][5]

 [1]: http://docs.firstdata.com/org/gateway/node/224
 [2]: https://docs.firstdata.com/org/gateway/node/325
 [3]: http://docs.firstdata.com/org/gateway/node/154
 [4]: https://docs.firstdata.com/org/gateway/node/483
 [5]: http://docs.firstdata.com/org/gateway/node/318
