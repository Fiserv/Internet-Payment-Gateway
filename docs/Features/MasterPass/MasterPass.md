---
title: MasterPass
---

<p class="MsoBodyText">
  <span><span><span><span>MasterPass is a digital wallet solution provided by participating banks and supported by MasterCard. Users can store multiple cards from different brands in their digital wallet.</span></span></span></span>
</p>

<p class="MsoBodyText">
  <span><span><span><span>When making an online purchase, customers log into their digital wallets and select a stored card for the payment. It is important to note that customers will only be able to select the card brands that your gateway Store has been enabled for.</span></span></span></span>
</p>

<p class="MsoBodyText">
  &nbsp;
</p>

<h3 class="MsoBodyText">
  <span><span><span><span>Checkout Process with MasterPass</span></span></span></span>
</h3>

<p class="MsoBodyText">
  <span><span><span><span>The checkout process with MasterPass can be initiated with a “BUY WITH MasterPass” that you place on your website along with any other payment methods that you offer. When your customers click this button, you construct a <a href="https://docs.firstdata.com/org/gateway/node/321">‘sale’ or ‘preauth’ request</a> with the parameter ‘paymentMethod’ set to ‘masterpass’. This will take your customers to the MasterPass login screen. From there, they will be taken to the subsequent pages of the digital wallet, and finally, back to your web shop.</span></span></span></span>
</p>

<p class="MsoBodyText">
  <span><span><span><span>Alternatively, you can let your customers select MasterPass on First Data’s hosted payment page. To do this, simply do not submit the parameter ‘paymentMethod’.</span></span></span></span>
</p>

<p class="MsoBodyText">
  <span><span><span><span>Important to note prior to integration</span></span></span></span>
</p>

<li class="MsoBodyText">
  <span><span><span><span>The Billing Address for MasterPass transactions is associated with the card stored inside the wallet, so there will be no additional entry requirements for Billing Address when a customer uses MasterPass as a transaction method. The Billing Address stored in the wallet will also automatically override any billing address data you may send within your transaction request to the gateway - you will always receive the Billing Address from the wallet in the transaction response.</span></span></span></span>
</li>
<li class="MsoBodyText">
  <span><span><span><span>You can send the <a href="https://docs.firstdata.com/org/gateway/node/212">Shipping Address</a> with your transaction request and your customers will not have to select or provide it again inside the wallet, reducing the time to check out. This is particularly useful, for example, for software products that available as downloads, where a shipping address is not required.</span></span></span></span>
</li>
<li class="MsoBodyText">
  <span><span><span><span>In some cases, the shipping address, and therefore the shipping fee, will not be clear when your customer enters the wallet process by click the ‘BUY WITH Masterpass’ button. Where this is the case, you can send additional parameters in your transaction request that allow you to present a final amount to your customers when they land on the confirmation page after returning from the wallet.</span></span></span></span>
</li>

<p class="MsoBodyText">
  <span><span><span><span>Set ‘reviewOrder’ to ‘true’ in order to indicate that the final transaction amount must be reviewed by your customer before completion. In addition, you will need to provide the URL for your confirmation page in the parameter ‘reviewURL’</span></span></span></span>
</p>

<p class="MsoBodyText">
  <span><span><span><span>When your customer confirms the final amount, you need to send a request to finalize the transaction to the ‘redirectURL’ that you will have received in the response from the gateway. This final request must include:</span></span></span></span>
</p>

<li class="MsoBodyText">
  <span><span><span><span>oid</span></span></span></span>
</li>
<li class="MsoBodyText">
  <span><span><span><span>ipgTransactionId</span></span></span></span>
</li>
<li class="MsoBodyText">
  <span><span><span><span>subtotal</span></span></span></span>
</li>
<li class="MsoBodyText">
  <span><span><span><span>shipping</span></span></span></span>
</li>
<li class="MsoBodyText">
  <span><span><span><span>vattax</span></span></span></span>
</li>
<li class="MsoBodyText">
  <span><span><span><span>chargetotal</span></span></span></span>
</li>
<li class="MsoBodyText">
  <span><span><span><span>currency</span></span></span></span>
</li>
<li class="MsoBodyText">
  <span><span><span><span>hashExtended</span></span></span></span>
</li>

<p class="MsoBodyText">
  <span><span><span><span>Note that you can also set a static ‘reviewURL’ via the Virtual Terminal. (Customization -> Online store integration -> Define the URLs for the integration with your online store section).</span></span></span></span>
</p>

<h4 class="MsoBodyText">
  <span><span><span><span>3-D Secure with MasterPass</span></span></span></span>
</h4>

<p class="MsoBodyText">
  <span><span><span><span>When your store is activated for <a href="https://docs.firstdata.com/org/gateway/node/73">3-D Secure</a>, the same settings will apply to your MasterPass transactions. However, MasterCard will handle the authentication process in the wallet (MasterPass Advanced Checkout), where supported programs are limited to MasterCard SecureCode and Verified by Visa – there is no American Express SafeKey. </span></span></span></span>
</p>

<p class="MsoBodyText">
  <span><span><span><span>In this case, the parameter ‘authenticateTransaction’ can be used to dynamically steer the behavior for MasterPass – depending on the transaction amount. If you set this parameter to ‘false’, the transaction will be initiated using the MasterPass Basic Checkout, which does not include 3-D Secure authentication.</span></span></span></span>
</p>

<p class="MsoBodyText">
  <span><span><span><span>If you want to benefit from a liability shift for MasterPass transactions, you should use the MasterPass Advanced Checkout/3-D Secure and must enable 3-D Secure service so that it is invoked within the MasterPass wallet.</span></span></span></span>
</p>

<h4 class="MsoBodyText">
  Other Useful Information
</h4>

<li class="MsoBodyText">
  <span><span><span><span>MasterPass transactions do not require a card code (CVV2/CVC2/4DBC) unless stated in network rules. When a customer adds a card to the wallet, their card code is entered and checked once, and is not required again unless required by network rules.</span></span></span></span>
</li>
<li class="MsoBodyText">
  <span><span><span><span>Address Verification Service (AVS) is handled for MasterPass in the same way as any other transaction. However, as the billing address is associated with a card and stored in the wallet, the AVS is based on that and NOT the billing address provided by the customer in the webshop.</span></span></span></span>
</li>
<li class="MsoBodyText">
  <span><span><span><span>If you are a Betting/Casino Gambling merchant (MCC 7995), MasterPass is not available for you.</span></span></span></span>
</li>

<h3 class="MsoBodyText">
  &nbsp;
</h3>

<h3 class="MsoBodyText">
  <span><span><span><span>Activate MasterPass for Your Test Store</span></span></span></span>
</h3>

<li class="MsoBodyText">
  <span><span><span><span>Obtain credentials for the sandbox consumer accounts from the <a href="https://developer.mastercard.com/documentation/masterpass-merchant-integration-v7/7">online documentation</a> provided by MasterCard</span></span></span></span>
</li>
<li class="MsoBodyText">
  <span><span><span><span>Make sure your gateway test Store ID is enabled for MasterPass</span></span></span></span>
</li>
