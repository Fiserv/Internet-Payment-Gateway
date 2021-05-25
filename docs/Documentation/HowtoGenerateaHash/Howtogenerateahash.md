---
title: How to generate a hash
---

If you are using an HTML form to initiate the _sale_ or _preauth_ transaction, your request needs to include a security hash for verification of&nbsp;the message integrity.

The Hash (parameter _hashExtended_) needs to be calculated using all&nbsp;<span lang="EN-US"><span><span><span>non-empty gateway</span></span></span></span>&nbsp;<span lang="EN-US"><span><span><span>specified</span></span></span></span> request parameters in ascending order of the parameter names,&nbsp;<span lang="EN-US"><span><span><span>where the shared secret (parameter <em>sharedsecret</em>) must be used as the secret key for calculating the hash value</span></span></span></span>.&nbsp;

<span lang="EN-US"><span><span><span>The request parameters that are not specified in our solution can still be submitted in your request to the gateway, but they must be excluded from the hash calculation.&nbsp;&nbsp;They will be ignored during processing and returned back in the response.&nbsp;&nbsp;</span></span></span></span>

When you are using Direct Post, there is also an option where you do not need to know the card details (PAN, CVV and Expiry Date) for the hash calculation. This will be managed with a specific setting performed on your store. Please contact your local support team if you want to enable this feature.

&nbsp;

### Creating the hash with all parameters (_hashExtended_)

<span><span><span lang="EN-US">Transaction request values used for the hash calculation </span></span></span><span lang="EN-US"><span><span><span>can be considered as a set of mandatory as well as optional gateway</span></span></span></span>&nbsp;<span lang="EN-US"><span><span><span>specified request parameters depending on the way&nbsp;you decide to build your request. See an example below</span></span></span></span><span><span><span lang="EN-US">: </span></span></span>

  * <span><span><span lang="EN-US">chargetotal= 13.00</span></span></span>
  * <span><span><span lang="EN-US">currency= 978</span></span></span>
  * <span><span><span><span><span><span><span lang="EN-US"><span>hash_algorithm=</span></span><span lang="EN-US"><span><span>HMACSHA256</span></span></span></span></span></span></span></span></span>
  * <span><span><span lang="EN-US">paymentMethod=M</span></span></span>
  * <span><span><span lang="EN-US">responseFailURL=<a href="https://localhost:8643/webshop/response_failure.jsp"><span lang="EN-GB"><span>https://localhost:8643/webshop/response_failure.jsp</span></span></a></span></span></span>
  * <span><span><span lang="EN-US">responseSuccessURL=<a href="https://localhost:8643/webshop/response_success.jsp"><span lang="EN-GB"><span>https://localhost:8643/webshop/response_success.jsp</span></span></a></span></span></span>
  * <span><span><span lang="EN-US">storename=10123456789</span></span></span>
  * <span><span><span lang="EN-US">timezone=</span> <span lang="EN-US">Europe/Berlin</span></span></span>
  * <span><span><span lang="EN-US">transactionNotificationURL=<a href="https://localhost:8643/webshop/transactionNotification"><span lang="EN-GB"><span>https://localhost:8643/webshop/transactionNotification</span></span></a></span></span></span>
  * <span><span><span lang="EN-US">txndatetime=2020:04:17-17:32:41</span></span></span>
  * <span><span><span lang="EN-US">txntype=sale</span></span></span>
  * <span><span><span lang="EN-US">sharedsecret=sharedsecret&nbsp;</span></span></span><span lang="EN-US"><span><span><span>to be used as the secret key for calculating the hash value.</span></span></span></span>

<span><span><span><span lang="EN-US"><span><span>The steps below provide the guidelines on how to calculate a hash, while using the values from our example.</span></span></span></span></span></span>

<span><span><span lang="EN-US"><strong>Step 1.</strong>&nbsp; </span><span lang="EN-US">Extended</span><span lang="EN-US"> hash needs to be calculated using all </span></span></span><span lang="EN-US"><span><span><span>non-empty gateway&nbsp;specified </span></span></span></span><span><span><span lang="EN-US">request parameters in ascending order of the parameter names. Join the parameters’ values to one string with pipe separator (use only parameters’ values and not the parameters’ names).</span></span></span>

<pre><span><span><span lang="EN-US">stringToExtendedHash = 13.00|978|</span></span></span><span lang="EN-US"><span><span><span>HMACSHA256|</span></span></span></span><span><span><span lang="EN-US">M|https://localhost:8643/webshop/response_failure.jsp|https://localhost:8643/webshop/response_success.jsp|10123456789|Europe/Berlin|https://localhost:8643/webshop/transactionNotification|2020:04:17-17:32:41|sale</span></span></span>
</pre>

<span><span><span lang="EN-US">The corresponding hash string does not include ‘sharedsecret’, which has to be used as the secret key for the HMAC instead.</span></span></span>

<span><span><span lang="EN-US"><strong>Step 2.</strong> Pass the created string to the HMACSHA256 algorithm with the shared secret as a key for calculating the hash value.</span></span></span>

<pre><span><span><span lang="EN-US"><span>HmacSHA256</span></span><span lang="EN-US">(stringToExtendedHash</span><span lang="EN-US">, sharedsecret)</span></span></span></pre>

<span><span><span lang="EN-US"><strong>Step 3.</strong> Use the value returned by the HMACSHA256 algorithm and submit it to our payment gateway in the given form.</span></span></span>

<pre><span lang="EN-US"><span><span><span>nI+XkhDBx27D31gte3b1TOfNlGhXiyf7j+JZ/bQwxsM=</span></span></span></span>
</pre>

<pre><span><span><span lang="EN-US"><span>&lt;input type="hidden" name="hashExtended" value="</span></span></span></span><span lang="EN-US"><span><span><span>nI+XkhDBx27D31gte3b1TOfNlGhXiyf7j+JZ/bQwxsM=</span></span></span></span><span><span><span lang="EN-US"><span>"/&gt;</span></span></span></span></pre>

&nbsp;

### Hash Generation Code Examples

> [PHP][1]  
> [ASP][2]

 [1]: https://docs.firstdata.com/org/gateway/node/323
 [2]: https://docs.firstdata.com/org/gateway/node/324
