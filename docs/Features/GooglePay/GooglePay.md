Google Pay
---

<img alt="Google Pay logo" data-align="left" data-entity-type="file" data-entity-uuid="36a5cfb6-5b57-4386-92a9-cab37da62e49" height="63" src="https://raw.githubusercontent.com/Fiserv/Internet-Payment-Gateway/develop/assets/images/GooglePaylogo.png" width="103" />

&nbsp;

&nbsp;

Google Pay is the fast, simple way to pay in millions of places – online, in stores, and more. It brings together everything you need at checkout and keeps your information safe and secure.

<span><span><strong><span><span><span><span>User Action:</span></span></span></span></strong><span><span><span><span> the buyer taps the "Google Pay" button, and then selects a payment method an</span></span></span></span><span><span><span><span>d shipping address.</span></span></span></span></span></span>

<span><span><strong><span><span><span><span>If the purchase originates from a third-party site</span></span></span></span></strong><img alt="Google Pay" data-align="right" data-entity-type="file" data-entity-uuid="9e0eb0b7-5aab-4567-b52d-7073ec5d8e0f" src="https://raw.githubusercontent.com/Fiserv/Internet-Payment-Gateway/develop/assets/images/GooglePay_0.png" /></span></span>

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

&nbsp;

<span><span><span><strong><span><span>Google Pay Integration</span></span></strong></span></span></span>

<span><span><span><strong>Overview</strong></span></span></span>

<span><span><span>Google Pay enables developers to add payment processing to merchants’ Android-compatible apps and on Chrome on Android. These APIs allow consumers to pay with any credit card they have stored in their Google account, including any cards they may have previously set up on their Android Pay digital wallet. Consumers may also add a new payment account.</span></span></span>

<span><span><span>The target audience for this document is a developer who wants to use Google Pay in their payment application.</span></span></span>

&nbsp;

<span><span><span><strong>Merchant Boarding</strong></span></span></span>

Please reach out to your local Integration Support team for getting your account enabled.

<span><span><span><strong>Note: The Integration team will share a Sample Application to generate Google Encrypted payloads</strong></span></span></span>

<span><span><span><strong>Prerequisites to build and run the sample Application</strong></span></span></span>

<span><span><span>Developers wishing to use the Fiserv Google Pay sample application will need the following software and hardware:</span></span></span>

  * <span><span><span>Google Play Services version 18.0.0&nbsp;</span></span></span>
  * <span><span><span>A physical device or an emulator to use for developing and testing. Google Play services can only be installed on an emulator with an AVD that runs Google APIs platform based on Android 4.4 or higher.</span></span></span>
  * <span><span><span>The latest version of Android Studio.&nbsp;This includes:<br /> o&nbsp;The latest version of the AndroidSDK, including the SDK Tools component. The SDK is available from the</span></span></span>

<span><span><span>Android SDK Manager<br /> o&nbsp;JavaJRE(JDKfordevelopment) as per Android SDK requirements.</span></span></span>

<span><span><span>Your project should be able to compile against Android 4.4 (KITKAT) or higher.</span></span></span>

<span><span><span>For more details, please refer&nbsp;<a href="https://developers.google.com/pay/api/android/guides/setup"><span><span>https://developers.google.com/pay/api/android/guides/setup</span></span></a></span></span></span>

<span><span><span><strong>Changes to be made in the Application&nbsp;</strong></span></span></span>

<span><span><span><span><span><span><span>The following parameters need to be defined&nbsp;</span></span></span></span></span></span></span>

<span><span><span><span><span><span><span>a. Merchant ID</span></span></span></span></span></span></span>

<span><span><span><span><span><span><span>b. Merchant Token</span></span></span></span></span></span></span>

<span><span><span><span><span><span><span>c. APIKey</span></span></span></span></span></span></span>

<span><span><span><span><span><span><span>d. APISecret</span></span></span></span></span></span></span>

<span><span><span><span><span><span><span>Define the Fiserv Object Parameters: Parameters must be updated in the following files:&nbsp;</span></span></span></span></span></span></span>

<span><span><span><span><span><span><span>•&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Constants.java</span></span></span></span></span></span></span>

<span><span><span><span><span><span><span>•&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; EnvData.java</span></span></span></span></span></span></span>

&nbsp;

<span><span><span>Update the&nbsp;Constants.java&nbsp;file with the Merchant ID and Gateway Tokenization parameters. Note that:</span></span></span>

  
<span><span><span>•&nbsp;The Merchant ID will be shared by the Integration team and<br /> •&nbsp;The Gateway Tokenization parameter defaults to ‘firstdata’.&nbsp;</span></span></span>

<span><span><span><span><span><span><span>In the&nbsp;EnvData.java&nbsp;file, set the following environment variables, which will be shared by the Integration Team:</span></span></span></span></span></span></span>

&nbsp;

  * <span><span><span><span><span><span><span><span>APIKey –</span></span></span></span></span></span></span></span>
  * <span><span><span><span><span><span><span><span>Token –&nbsp;</span></span></span></span></span></span></span></span>
  * <span><span><span><span><span><span><span><span>APISecret –&nbsp;</span></span></span></span></span></span></span></span>

&nbsp;

<span><span><span><span><span><span><span><span>envMap.put("CERT", new EnvPropertiesImpl( "CERT", </span></span></span></span></span></span></span></span>

<span><span><span><span><span><span><span><span>&nbsp;"</span></span></span><span><span><span>https://cert.api.firstdata.com/gateway/v1/payments</span></span></span><span><span><span>", </span></span></span></span></span></span></span></span>

<span><span><span><span><span><span><span><span>&nbsp;"---------", "----------", "-----------")); </span></span></span></span></span></span></span></span>

&nbsp;

<span><span><span><span><span><span><span>gatewayMerchantId and the APIGEE credentials will be provided by the Integration Team</span></span></span></span></span></span></span>

<span><span><span><span>&nbsp;</span></span></span></span>

<span><span><span><strong>Credit Card for Testing</strong></span></span></span>

<span><span><span>Note that even for testing purpose; the credit card information used in the app must be attached to an active account.&nbsp;</span></span></span>

<span><span><span>The standard test cards will not be validated by Google and will fail in processing.</span></span></span>

&nbsp;

<span><span><span><strong>Execute Authorize and Purchase Request</strong></span></span></span>

<span><span><span>Fiserv Header Authorization Parameter</span></span></span>

<span><span><span>The Authorization parameter, required as part of the Header for a Fiserv API transaction, is created as follows:</span></span></span>

<span><span><span>Construct the data param by appending the following parameters in the order shown:</span></span></span>

<span><span><span>apikey – the developer’s API key</span></span></span>

<span><span><span>nonce – A secure random number</span></span></span>

<span><span><span>timestamp – Epoch timestamp in milliseconds</span></span></span>

<span><span><span>token – the Merchant Token&nbsp;</span></span></span>

<span><span><span>payload – The actual body content passed as the POST request&nbsp;</span></span></span>

<span><span><span><span>&nbsp;</span></span></span></span>

<span><span><span><strong>Google Pay APK Installation to Device</strong></span></span></span>

  * <span><span><span><span>Once the downloaded code for the sample app&nbsp;is built successfully in Android Studio, build the APK and install it on your device.</span></span></span></span>
  * <span><span><span><span>Once the APK is installed, select the Open option to access the application. The screenshots below show the sample application installed on the test device (nonPROD environment), and the response from a payment processed in the First Data nonPROD environment/Google test environment.</span></span></span></span>

<span><span><span>Note that the Payment Details page cannot be captured for security reasons.</span></span></span>

<img alt="app" data-entity-type="file" data-entity-uuid="9ba30641-2c1b-4523-b713-4f136184c200" src="https://raw.githubusercontent.com/Fiserv/Internet-Payment-Gateway/develop/assets/images/15.png" /> 

<span><span><span><strong>Sample Google Pay Request:</strong></span></span></span>

<pre><span><span><span>{</span></span></span>

<span><span><span>  "requestType": "WalletPreAuthTransaction",</span></span></span>

<span><span><span>  "walletPaymentMethod": {</span></span></span>

<span><span><span>    "walletType": "EncryptedGooglePayWalletPaymentMethod",</span></span></span>

<span><span><span>    "encryptedGooglePay": {</span></span></span>

<span><span><span>      "data": {</span></span></span>

<span><span><span>        "encryptedMessage": "8nxjB9mr2tWZeDRQRcGN91UUnb7AioGp3oRo8kmQ6lyvJZiqD7PJlbRCYElNqUmr6Z8zK7b2gO9MKOjpnTCqH0qAe2vuIlwNXB60M2Lh7Qfl3bVgWzwF/FfFcenVW381hoItYi8AjWnWoydz1XMTEv2qhqUG03mEnRXdMyDyk6KKZXoW8Qc0p1F1thbxxu8weU8CZbZsWGGTjB42cilIqLVbribcOAG8Oas1AcgefFsu2hwp4gdSuOg7wmeSV7XKsGQzzVy85qtjuqET2XYzJE3K/Wh9QKkhu5P9Ms5s1+Smr2IjRyidqQa88SxQplrVoo9+PvT0bxFcMspBmO3pLkuaZSUBy++dL2fefcxNJvGCFfFhdxW9DojuuQxgpeu7RAQUsGLyFmr/4ZfBxt882xTmpX9MRx5CAudl9qUgBfKdwWwMX35qSbDTm1ju5XXzNh94VebjD3bB9Zj8qgbmUOr/+6OQLhoFJyBCXgx3EEH8hBwNVFrss/SLwQvFhZh62eO6lOtnmbOtP1yTDDVqGDBfai5SwAmM+KTcc9SGv/xDC+cWe8ck+aCBkG4HoRPapUVMZ3JIgV7yzTsVLJE\\u003d",</span></span></span>

<span><span><span>        "ephemeralPublicKey": "BGH3fRFdoAobYrAlxnZOCYzkH84Cna92IZxtgsU36CMDaqSaDYb9/LsY8qw+vMtlBnwsUg/YVMOeeKp+qDkOWb4\\u003d",</span></span></span>

<span><span><span>        "tag": "nvmOUNpnOTZULLhMxT/hWCHzH/4f7gGpfvQgwl3p8ng\\u003d"</span></span></span>

<span><span><span>      },</span></span></span>

<span><span><span>      "signature": "MEUCIFWTRWUZAOM5nfJC79FtJm56olnbwG4H5uWWxAUWAquiAiEA24j/BcOroeISsdJzYsyoVi8wzu4tnmKw+jdsGfuvPko=",</span></span></span>

<span><span><span>      "version": "ECv1"</span></span></span>

<span><span><span>    }</span></span></span>

<span><span><span>  },</span></span></span>

<span><span><span>  "transactionAmount": {</span></span></span>

<span><span><span>    "total": "1200",</span></span></span>

<span><span><span>    "currency": "USD"</span></span></span>

<span><span><span>  }</span></span></span>

<span><span><span>}</span></span></span></pre>

&nbsp;

<span><span><span><strong>Sample Google Pay Response:</strong></span></span></span>

<pre><span><span><span><span><span><span><span>{</span></span></span></span></span></span></span>

<span><span><span><span><span><span><span>  "clientRequestId": "741666",</span></span></span></span></span></span></span>

<span><span><span><span><span><span><span>  "apiTraceId": "rrt-01b12ed35a0f32f98-c-ea-12855-958124-1",</span></span></span></span></span></span></span>

<span><span><span><span><span><span><span>  "ipgTransactionId": "84290618651",</span></span></span></span></span></span></span>

<span><span><span><span><span><span><span>  "orderId": "R-3f8d4c21-66c9-47d4-bb59-c7f167ace094",</span></span></span></span></span></span></span>

<span><span><span><span><span><span><span>  "transactionType": "SALE",</span></span></span></span></span></span></span>

<span><span><span><span><span><span><span>  "transactionOrigin": "ECOM",</span></span></span></span></span></span></span>

<span><span><span><span><span><span><span>  "paymentMethodDetails": {</span></span></span></span></span></span></span>

<span><span><span><span><span><span><span>    "paymentCard": {</span></span></span></span></span></span></span>

<span><span><span><span><span><span><span>      "expiryDate": {</span></span></span></span></span></span></span>

<span><span><span><span><span><span><span>        "month": "**",</span></span></span></span></span></span></span>

<span><span><span><span><span><span><span>        "year": "****"</span></span></span></span></span></span></span>

<span><span><span><span><span><span><span>      },</span></span></span></span></span></span></span>

<span><span><span><span><span><span><span>      "bin": "******",</span></span></span></span></span></span></span>

<span><span><span><span><span><span><span>      "last4": "****",</span></span></span></span></span></span></span>

<span><span><span><span><span><span><span>      "brand": "AMEX"</span></span></span></span></span></span></span>

<span><span><span><span><span><span><span>    },</span></span></span></span></span></span></span>

<span><span><span><span><span><span><span>    "paymentMethodType": "PAYMENT_CARD"</span></span></span></span></span></span></span>

<span><span><span><span><span><span><span>  },</span></span></span></span></span></span></span>

<span><span><span><span><span><span><span>  "country": "USA",</span></span></span></span></span></span></span>

<span><span><span><span><span><span><span>  "terminalId": "1588390",</span></span></span></span></span></span></span>

<span><span><span><span><span><span><span>  "transactionTime": 1579707422,</span></span></span></span></span></span></span>

<span><span><span><span><span><span><span>  "approvedAmount": {</span></span></span></span></span></span></span>

<span><span><span><span><span><span><span>    "total": 12.00,</span></span></span></span></span></span></span>

<span><span><span><span><span><span><span>    "currency": "USD",</span></span></span></span></span></span></span>

<span><span><span><span><span><span><span>    "components": {</span></span></span></span></span></span></span>

<span><span><span><span><span><span><span>      "subtotal": 12.00</span></span></span></span></span></span></span>

<span><span><span><span><span><span><span>    }</span></span></span></span></span></span></span>

<span><span><span><span><span><span><span>  },</span></span></span></span></span></span></span>

<span><span><span><span><span><span><span>  "transactionStatus": "APPROVED",</span></span></span></span></span></span></span>

<span><span><span><span><span><span><span>  "schemeTransactionId": "010022066071191",</span></span></span></span></span></span></span>

<span><span><span><span><span><span><span>  "processor": {</span></span></span></span></span></span></span>

<span><span><span><span><span><span><span>    "referenceNumber": "84290618651 ",</span></span></span></span></span></span></span>

<span><span><span><span><span><span><span>    "authorizationCode": "OK4090",</span></span></span></span></span></span></span>

<span><span><span><span><span><span><span>    "responseCode": "00",</span></span></span></span></span></span></span>

<span><span><span><span><span><span><span>    "network": "AMEX",</span></span></span></span></span></span></span>

<span><span><span><span><span><span><span>    "associationResponseCode": "000",</span></span></span></span></span></span></span>

<span><span><span><span><span><span><span>    "responseMessage": "APPROVAL",</span></span></span></span></span></span></span>

<span><span><span><span><span><span><span>    "avsResponse": {</span></span></span></span></span></span></span>

<span><span><span><span><span><span><span>      "streetMatch": "Y",</span></span></span></span></span></span></span>

<span><span><span><span><span><span><span>      "postalCodeMatch": "Y"</span></span></span></span></span></span></span>

<span><span><span><span><span><span><span>    }</span></span></span></span></span></span></span>

<span><span><span><span><span><span><span>  },</span></span></span></span></span></span></span>

<span><span><span><span><span><span><span>  "additionalDetails": {</span></span></span></span></span></span></span>

<span><span><span><span><span><span><span>    "walletProvider": "GOOGLE_PAY"</span></span></span></span></span></span></span>

<span><span><span><span><span><span><span>  }</span></span></span></span></span></span></span>

<span><span><span><span><span><span><span>}</span></span></span></span></span></span></span></pre>

&nbsp;

 [1]: https://support.google.com/pay/answer/7454247?hl=en
