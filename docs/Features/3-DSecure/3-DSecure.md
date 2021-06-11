3-D Secure 
---

3-D Secure is a messaging protocol developed by EMVCo to support app-based&nbsp;authentication and integration with digital wallets, as well as traditional browser based eCommerce transactions. The solution introduces&nbsp;many benefits to the&nbsp;marketplace as they will reflect the payment community’s objective to secure&nbsp;consumer eCommerce transactions while optimizing the user experience. <span></span>

<span>If your merchant account is enabled for 3-D Secure, all <em>sale </em>or <em>preauth </em>transactions that you initiate by posting an HTML form will by default go through the 3-D Secure process without the need for you to do anything, i.e. cardholders with an enrolled card will see a page from the card issuer to enter the password unless the card issuer decides not to check it.</span>

<span>After the authentication, we bring the cardholder back to your webstore.&nbsp;</span><span><span><span><span lang="EN-US"><span><span>If your credit card agreement includes 3-D Secure and your Merchant ID has been activated to use this service, you do not need to modify your payment page.</span></span></span></span></span></span>

<span><span><span><span lang="EN-US"><span><span>The following represents an example of a ‘Sale’ transaction request with minimum set of fields including optional “Challenge Indicator” element:</span></span></span></span></span></span>

<pre>&lt;!-- #include file="ipg-util.asp"--&gt;
&lt;html&gt;
&lt;head&gt;&lt;title&gt;IPG Connect Sample for ASP&lt;/title&gt;&lt;/head&gt;
&lt;body&gt;
&lt;p&gt;&lt;h1&gt;Order Form&lt;/h1&gt;&lt;/p&gt;
&lt;form method="post" action=" https://test.ipg-online.com/connect/gateway/processing "&gt;
&nbsp; &nbsp; &lt;input type="hidden" name="txntype" value="sale"&gt;
    &lt;input type="hidden" name="checkoutoption" value="combinedpage"&gt;
&nbsp; &nbsp; &lt;input type="hidden" name="timezone" value="Europe/Berlin"/&gt;
&nbsp; &nbsp; &lt;input type="hidden" name="txndatetime" value="&lt;% getDateTime() %&gt;"/&gt;
&nbsp; &nbsp; &lt;input type="hidden" name="hash_algorithm" value="HMACSHA256"/&gt;
&nbsp;   &lt;input type="hidden" name="hashExtended" value="&lt;% call createExtendedHash( "13.00","978" ) %&gt;"/&gt;
&nbsp; &nbsp; &lt;input type="hidden" name="storename" value="110995000" /&gt;
&nbsp; &nbsp; &lt;input type="hidden" name="mode" value="payonly"/&gt;
&nbsp; &nbsp; &lt;input type="hidden" name="paymentMethod" value="V"/&gt;
&nbsp; &nbsp; &lt;input type="text" name="chargetotal" value="13.00" /&gt;
&nbsp; &nbsp; &lt;input type="hidden" name="currency" value="978"/&gt;
&nbsp; &nbsp; &lt;input type="hidden" name="authenticateTransaction" value="true"/&gt;
&nbsp; &nbsp; &lt;input type="text" name="threeDSRequestorChallengeIndicator" value=”1”/&gt;
&nbsp; &nbsp; &lt;input type="submit" value="Submit"&gt;
&lt;/form&gt;
&lt;/body&gt;
&lt;/html&gt;
</pre>

The result of the transaction will be sent back to the defined ‘responseSuccessURL’ or ‘responseFailURL’ as hidden fields:

<pre>{txndate_processed=20/04/10 13:37:33, 
ccbin=542606, 
timezone=CET, 
oid=C-2101f68a-45e9-4f3c-a6da-1337d5574717, 
cccountry=N/A, 
expmonth=12, 
currency=978, 
chargetotal=13.99, 
approval_code=Y:ECI2/5:Authenticated, 
hiddenSharedsecret=sharedsecret, 
hiddenTxndatetime=2019:04:10-13:37:08, 
expyear=2024, 
response_hashExtended=927d3c3108d596c593f74fd79184ece7c33103fe, 
<strong>response_code_3dsecure=1</strong>, 
hiddenStorename=12345678, 
transactionNotificationURL=https://test.ipg-online.com/webshop/transactionNotification, 
tdate=1554903428, 
ignore_refreshTime=on, 
ccbrand=VISA, 
txntype=sale, 
paymentMethod=V, 
txndatetime=2020:04:10-13:37:08, 
cardnumber=(VISA) ... 4979, 
ipgTransactionId=84120276797, 
status=APPROVED}
</pre>

<span><span><span><span lang="EN-US"><span><strong>Challenge indicator available values for 3DS protocol version 2.1 are</strong>:</span></span></span></span></span>

<span><span><span><span lang="EN-US"><span>01 = No preference (You have no preference whether a challenge should be performed. This is the default value)<br /> 02 = No challenge requested (You prefer that no challenge should be performed.)<br /> 03 = Challenge requested: 3DS Requestor Preference (You prefer that a challenge should be performed)<br /> 04 = Challenge requested: Mandate (There are local or regional mandates that mean that a challenge must be &nbsp;&nbsp;performed)</span></span></span></span></span>

<span lang="EN-US"><span><span>In case you have not used billing and shipping details in your authentication request before, please consider to include them to&nbsp;lower the 3-D Secure authentication declines.</span></span></span>

&nbsp;

### 3-D Secure Information in the Transaction Response

<span><span><span lang="EN-GB">Upon completion, the transaction details will be sent back to the defined <em>responseSuccessURL</em> or <em>responseFailURL</em> as hidden fields.</span></span></span>

<span><span><span lang="EN-GB">Return code indicating the classification of the transaction:</span></span></span>

<span><span><span lang="EN-GB">1 – Successful authentication (VISA ECI 05, MasterCard ECI 02)<br /> 2 – Successful authentication without AVV (VISA ECI 05, MasterCard ECI 02)<br /> 3 – Authentication failed&nbsp;/ incorrect password / authentication rejected by the DS or ACS&nbsp;(transaction declined by the Gateway)<br /> 4 – Authentication attempt (VISA ECI 06, MasterCard ECI 01)<br /> 5 – Unable to authenticate / DS not responding (VISA ECI 07) - relevant for 3DS 1.0<br /> 6 – Unable to authenticate / ACS or DS not responding (VISA ECI 07)<br /> 7 – Cardholder not enrolled for 3-D Secure (VISA ECI 07) - relevant for 3DS 1.0<br /> 8 – Invalid 3-D Secure values received&nbsp;</span></span></span>

&nbsp;

#### Alternative Options

  
>&nbsp;[REST API Integration][1]

  
>&nbsp;[SOAP API Integration][2]

  
> [Split Authentication and Authorization into two steps][3]

&nbsp;

### <span>Enabling/Disabling 3-D Secure on a Transaction-by-Transaction Basis</span>

<span>The optional parameter <em>authenticateTransaction</em></span> <span></span><span>can be used in case you want to send specific transactions without 3-D Secure. &nbsp;</span>

Check out how on our [Form Fields for Specific Functionalities][4] page

### Dynamic 3-D Secure

<span lang="EN-US">With the Dynamic 3-D Secure product option you can exclude specific card transactions from the 3-D Secure authentication based on a certain country selection (i.e.: issuing country) e.g.: Germany, Switzerland and Austria, while applying the standard 3-D Secure authentication process for other transactions with card from other countries.</span>

Check out our [Dynamic 3-D Secure][5] page.

### &nbsp;

### Additional Information

  * <span><span><span lang="EN-GB">In principle, it may occur that 3-D Secure authentications cannot be processed successfully for technical reasons.</span></span></span> <span><span><span lang="EN-GB">If one of the systems involved in the authentication process is temporarily not responding, the payment transaction will be processed as a “regular” eCommerce transaction (ECI 7). <strong>A liability shift to the card issuer for possible chargebacks is not warranted in this case</strong>. If you prefer that such transactions shall not be processed at all, our technical support teams can block them for your Store on request.</span></span></span>  
    &nbsp;
  * <span><span><span lang="EN-GB">Credit card transactions with 3-D Secure hold in a pending status while cardholders search for their password or need to activate their card for 3-D Secure during their shopping experience. During this time when the final transaction result of the transaction is not yet determined, the payment gateway sets the Approval Code to „?:waiting 3dsecure“. If the session expires before the cardholder returns from the 3-D Secure dialogue with his bank, the transaction will be shown as “N:-5103:Cardholder did not return from ACS”.</span></span></span>  
    &nbsp;
  * <span><span><span lang="EN-GB">Please note that the technical process of 3-D Secure transactions differs in some points compared to a normal transaction flow. If you already have an existing shop integration and plan to activate 3-D Secure subsequently, we recommend performing some test transactions on our test environment</span></span></span>, test data producing different authentication results can be found here:&nbsp;[3-D Secure Test Data][6] 
    &nbsp;

 [1]: https://docs.firstdata.com/org/gateway/node/1636
 [2]: https://docs.firstdata.com/org/gateway/node/456
 [3]: http://docs.firstdata.com/org/gateway/node/95
 [4]: https://docs.firstdata.com/org/gateway/node/455
 [5]: https://docs.firstdata.com/org/gateway/node/468
 [6]: https://docs.firstdata.com/org/gateway/node/1507
