---
title: Apple Pay
author: lovenish.sidana@firstdata.com
---

<img alt="Apple Pay logo" data-align="left" data-entity-type="file" data-entity-uuid="1b7e6d55-b5bd-4b9a-97fb-b07773dd5129" src="Apple%20Pay%20logo.png" />

&nbsp;

&nbsp;

Apple Pay enables secure, simple checkouts in your app or on your website.

User Action: the buyer taps the Apple Pay button in the app or on the website, selects the payment card and uses the Touch-ID to complete the transaction.

  * The Merchant App communities with the merchant server and creates a transaction ID
  * The Merchant App obtains the encrypted transaction payload (The tokenized card data "DPAN", Cryptogram, and transaction details) from Apple's Pass Kit Framework
  * The Merchant App sends the encrypted transaction payload to processor API using the Apple Pay SDK
  * Processor API decrypts the encrypted transaction payload and processes the transaction
  * Processor API responds back to the Merchant App (through the SDK) with either an approval or decline

To get more information on participating banks and countries for Apple Pay, [click here][1].

<span><span>Refer to our <a href="https://github.com/payeezy/payeezy_apple_pay/raw/master/guide/apple_pay081215.pdf">Integration guide</a> for detailed information on how to integrate Apple Pay.</span></span>

&nbsp;

<img alt="Apple Pay" data-align="center" data-entity-type="file" data-entity-uuid="670aed74-c6f2-419e-8208-26b4099a76a3" src="Apple%20Pay.png" /> 

&nbsp;

 [1]: https://support.apple.com/en-us/ht204916
