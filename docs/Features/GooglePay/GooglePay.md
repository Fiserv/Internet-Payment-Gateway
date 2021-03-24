---
title: Google Pay
author: lovenish.sidana@firstdata.com
---

<img alt="Google Pay logo" data-align="left" data-entity-type="file" data-entity-uuid="36a5cfb6-5b57-4386-92a9-cab37da62e49" height="63" src="Google%20Pay%20logo.png" width="103" />

&nbsp;

&nbsp;

Google Pay is the fast, simple way to pay in millions of places – online, in stores, and more. It brings together everything you need at checkout and keeps your information safe and secure.

<span><span><strong><span><span><span><span>User Action:</span></span></span></span></strong><span><span><span><span> the buyer taps the "Google Pay" button, and then selects a payment method an</span></span></span></span><span><span><span><span>d shipping address.</span></span></span></span></span></span>

<span><span><strong><span><span><span><span>If the purchase originates from a third-party site</span></span></span></span></strong><img alt="Google Pay" data-align="right" data-entity-type="file" data-entity-uuid="9e0eb0b7-5aab-4567-b52d-7073ec5d8e0f" src="Google Pay_0.png" /></span></span>

  1. <span><span><span><span><span><span><span><span>The merchant/client server issues a credential request with the Merchant ID and Processor Name as First Data to Google.</span></span></span></span></span></span></span></span>
  2. <span><span><span><span><span><span><span><span>Google returns response with encrypted payment credentials signed with the First Data key to the merchant server.</span></span></span></span></span></span></span></span>
  3. <span><span><span><span><span><span><span><span>The Merchant sends the encrypted payload to First Data.</span></span></span></span></span></span></span></span>
  4. <span><span><span><span><span><span><span><span>First Data decrypts and validates the payload, and then processes the transaction and responds back to merchant with either an approval or decline response.</span></span></span></span></span></span></span></span>

<span><span><strong><span><span><span><span>If the purchase originates from a Google site:</span></span></span></span></strong></span></span>

  1. <span><span><span><span><span><span><span><span>Google initiates a purchase request to the merchant after the consumer confirms order.</span></span></span></span></span></span></span></span>
  2. <span><span><span><span><span><span><span><span>The merchant/client server issues a request with the Merchant ID and Processor Name </span></span></span></span></span></span><span><span><span><span><span><span>as First Data to Google.</span></span></span></span></span></span></span></span>
  3. <span><span><span><span><span><span><span><span>Google returns response with encrypted payment credentials signed with the First Data key to merchant server.</span></span></span></span></span></span></span></span>
  4. <span><span><span><span><span><span><span><span>The merchant sends the encrypted payload to First Data.</span></span></span></span></span></span></span></span>
  5. <span><span><span><span><span><span><span><span>First Data decrypts and validates the payload and process the transaction and respond back to merchant with either an approval or decline response.</span></span></span></span></span></span></span></span>

<span><span>&nbsp;</span></span>

To get more information on participating banks and countries for Google Pay, [click here][1].

<span><span>Refer to our <a href="https://github.com/payeezy/pay_with_google/tree/master/guide">Integration guide</a> for detailed information on how to integrate Google Pay.</span></span>

 [1]: https://support.google.com/pay/answer/7454247?hl=en
