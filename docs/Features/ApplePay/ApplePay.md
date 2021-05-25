Apple Pay
---

<img alt="Apple Pay logo" data-align="left" data-entity-type="file" data-entity-uuid="1b7e6d55-b5bd-4b9a-97fb-b07773dd5129" src="/files/ApplePaylogo.png" />

&nbsp;

&nbsp;

Apple Pay enables secure, simple checkouts in your app or on your website.

User Action: the buyer taps the Apple Pay button in the app or on the website, selects the payment card and uses the Touch-ID to complete the transaction.

  * The Merchant App communicates with the merchant server and creates a transaction ID
  * The Merchant App obtains the encrypted transaction payload (The tokenized card data "DPAN", Cryptogram, and transaction details) from Apple's Pass Kit Framework
  * The Merchant App sends the encrypted transaction payload to processor API using the Apple Pay SDK
  * Processor API decrypts the encrypted transaction payload and processes the transaction
  * Processor API responds back to the Merchant App (through the SDK) with either an approval or decline

To get more information on participating banks and countries for Apple Pay, [click here][1].

&nbsp;

<img alt="Apple Pay" data-align="center" data-entity-type="file" data-entity-uuid="670aed74-c6f2-419e-8208-26b4099a76a3" src="/files/ApplePay.png" /> 

&nbsp;

<span><span><span><strong><span><span>Apple Pay Integration</span></span></strong></span></span></span>

<span><span><span><strong>Merchant Boarding</strong></span></span></span>

<span><span><span>Please reach out to your local Integration Support team for getting your account enabled.</span></span></span>

<span><span><span><strong>CSR Generation </strong></span></span></span>

<span><span><span>Our Integration team will generate the CSR and share it with you&nbsp;along with the Merchant Identifier.</span></span></span>

<span><span><span><strong>Generate Payment Processing Certificate from Apple Portal</strong></span></span></span>

<span><span><span>Steps to create a Payment processing certificate in the Apple portal:</span></span></span>

  * <span><span><span>Login to apple 'Account' in developer.apple.com</span></span></span>
  * <span><span><span>In-order to generate certificate you must have a paid apple developer account or an organization account. New users must follow the prompts to set up a developer account. </span></span></span>
  * <span><span><span>Select Certificates, Identifiers and Profile : </span></span></span>

<img alt="Certificates, Identifiers and Profile " data-entity-type="file" data-entity-uuid="58e6fc53-9fdb-438e-9aba-f08c97090b6b" src="/sites/default/files/inline-images/12.1.png" /> 

  * <span><span><span>Select Identifier's and in the dropdown in the upper-right corner select merchant id</span></span></span>
  * <span><span><span>Enter a unique merchant id, and upload a valid CSR in .pem format. </span></span></span>
  * <span><span><span>Once successfully uploaded, apple provides the payment processing certificate and the merchant id will come up in the certificate section. </span></span></span>
  * <span><span><span>Download payment processing certificate and install in your computer by double clicking it. </span></span></span>
  * <span><span><span>The certificate should show up in the 'Key chain access' of your Macbook. </span></span></span>

<span><span><span><strong>Upload and register the apple development certificate for your machine</strong></span></span></span>

  * <span><span><span>Request a new certificate from your keychain access. </span></span></span>

<img alt="Request certificate" data-entity-type="file" data-entity-uuid="27c0d175-328d-4003-a750-a2a849079b53" src="/sites/default/files/inline-images/13_1.png" /> 

  * <span><span><span>Follow the prompt and request the certificate to be saved on file. </span></span></span>
  * <span><span><span>In the 'Certificate' section in the apple portal, click on the '+' and follow the prompt to request apple developer certificate for 'IOS' development.</span></span></span>
  * <span><span><span>Upload the requested certificate </span></span></span>
  * <span><span><span>Download and install the apple pay developer certificate. </span></span></span>
  * <span><span><span>Your machine is now setup for programming IOS app using Xcode. </span></span></span>

<span><span><span><strong>Set-up Provision Profile for the application</strong></span></span></span>

  * <span><span><span>In the 'Certificate, Identifier and Profile' section in the apple portal navigate to profile.</span></span></span>
  * <span><span><span>Click the '+' sign to create a new profile. </span></span></span>
  * <span><span><span>Choose, 'IOS' development and follow the prompts</span></span></span>
  * <span><span><span>In the capabilities select 'Apple Pay' and 'In-App Purchases' </span></span></span>
  * <span><span><span>You can also register the test devices here using, uuid. (Xcode also does this when the app is built on the phone)</span></span></span>
  * <span><span><span>Download the provision profile on to your mac. </span></span></span>

<span><span><span><strong>Set-up Project in Xcode</strong></span></span></span>

  * <span><span><span>Select new xcode project with a single view or import an existing project. </span></span></span>
  * <span><span><span>Register the app using the app-id in the apple portal under Identifier->appId</span></span></span>
  * <span><span><span>Go to Xcode->Preferences,->accounts and install the downloaded provision profile, your profile is now linked to your Xcode. </span></span></span>
  * <span><span><span>Click on your project, go to Signing & Capabilities select 'Automatically manage signing'.</span></span></span>
  * <span><span><span>'+ capabilities' add apple pay.</span></span></span>
  * <span><span><span>Under 'Apple Pay' click '+' and add the merchant id's registered in the portal, which in turn will be added to the entitlements file. </span></span></span>

<span><span><span>Now the Xcode is set-up for coding. </span></span></span>

<span><span><span>In the SDK enter the URL, api key and api secret and build the app:</span></span></span>

<img alt="SDK" data-entity-type="file" data-entity-uuid="9a233c5e-1a72-48ab-9d13-b73dc631a9ec" src="/sites/default/files/inline-images/14.2.png" /> 

  * <span><span><span>Merchant id: Enter any valid merchant id registered in the apple portal. This gives the capability for a single user to use multiple merchant id's</span></span></span>
  * <span><span><span>Amount: Enter the amount of the transaction</span></span></span>
  * <span><span><span>Transaction type: Select PreAuth or Sale. </span></span></span>
  * <span><span><span>Apple Pay Button: Click this to produce payment sheet and fingerprint authentication for the transaction. </span></span></span>

<span><span><span>Once the user authenticates the transaction the apple returns the payment token, using which the SDK generates the following payload:</span></span></span>

&nbsp;

<span><span><span><strong>Sample Apple Pay Request</strong></span></span></span>

<span><span><span>Endpoint: https://cert.api.firstdata.com/gateway/v2/payments</span></span></span>

<pre><span><span><span>{</span></span></span>

<span><span><span>   "walletPaymentMethod":{</span></span></span>

<span><span><span>      "walletType":"EncryptedApplePayWalletPaymentMethod",</span></span></span>

<span><span><span>      "encryptedApplePay":{</span></span></span>

<span><span><span>         "data":"hbreWcQg980mUoUCfuCoripnHO210lvtizOFLV6PTw1DjooSwik778bH/qgK2pKelDTiiC8eXeiSwSIfrTPp6tq9x8Xo2H0KYAHCjLaJtoDdnjXm8QtC3m8MlcKAyYKp4hOW6tcPmy5rKVCKr1RFCDwjWd9zfVmp/au8hzZQtTYvnlje9t36xNy057eKmA1Bl1r9MFPxicTudVesSYMoAPS4IS+IlYiZzCPHzSLYLvFNiLFzP77qq7B6HSZ3dAZm244v8ep9EQdZVb1xzYdr6U+F5n1W+prS/fnL4+PVdiJK1Gn2qhiveyQX1XopLEQSbMDaW0wYhfDP9XM/+EDMLaXIKRiCtFry9nkbQZDjr2ti91KOAvzQf7XFbV+O8i60BSlI4/QRmLdKHmk/m0rDgQAoYLgUZ5xjKzXpJR9iW6RWuNYyaf9XdD8s2eB9aBQ=",</span></span></span>

<span><span><span>         "header":{</span></span></span>

<span><span><span>            "applicationDataHash":"94ee059335e587e501cc4bf90613e0814f00a7b08bc7c648fd865a2af6a22cc2",</span></span></span>

<span><span><span>            "ephemeralPublicKey":"MFkwEwYHKoZIzj0CAQYIKoZIzj0DAQcDQgAEvR+anQg6pElOsCnC3HIeNoEs2XMHQwxuy9plV1MfRRtIiHnQ6MyOS+1FQ7WZR2bVAnHFhPFaM9RYe7/bynvVvg==",</span></span></span>

<span><span><span>            "publicKeyHash":"KRsyW0NauLpN8OwKr+yeu4jl6APbgW05/TYo5eGW0bQ=",</span></span></span>

<span><span><span>            "transactionId":"31323334353637"</span></span></span>

<span><span><span>         },</span></span></span>

<span><span><span>         "signature":"MIAGCSqGSIb3DQEHAqCAMIACAQExDzANBglghkgBZQMEAgEFADCABgkqhkiG9w0BBwEAAKCAMIIB0zCCAXkCAQEwCQYHKoZIzj0EATB2MQswCQYDVQQGEwJVUzELMAkGA1UECAwCTkoxFDASBgNVBAcMC0plcnNleSBDaXR5MRMwEQYDVQQKDApGaXJzdCBEYXRhMRIwEAYDVQQLDAlGaXJzdCBBUEkxGzAZBgNVBAMMEmQxZHZ0bDEwMDAuMWRjLmNvbTAeFw0xNTA3MjMxNjQxMDNaFw0xOTA3MjIxNjQxMDNaMHYxCzAJBgNVBAYTAlVTMQswCQYDVQQIDAJOSjEUMBIGA1UEBwwLSmVyc2V5IENpdHkxEzARBgNVBAoMCkZpcnN0IERhdGExEjAQBgNVBAsMCUZpcnN0IEFQSTEbMBkGA1UEAwwSZDFkdnRsMTAwMC4xZGMuY29tMFkwEwYHKoZIzj0CAQYIKoZIzj0DAQcDQgAErnHhPM18HFbOomJMUiLiPL7nrJuWvfPy0Gg3xsX3m8q0oWhTs1QcQDTT+TR3yh4sDRPqXnsTUwcvbrCOzdUEeTAJBgcqhkjOPQQBA0kAMEYCIQDrC1z2JTx1jZPvllpnkxPEzBGk9BhTCkEB58j/Cv+sXQIhAKGongoz++3tJroo1GxnwvzK/Qmc4P1K2lHoh9biZeNhAAAxggFSMIIBTgIBATB7MHYxCzAJBgNVBAYTAlVTMQswCQYDVQQIDAJOSjEUMBIGA1UEBwwLSmVyc2V5IENpdHkxEzARBgNVBAoMCkZpcnN0IERhdGExEjAQBgNVBAsMCUZpcnN0IEFQSTEbMBkGA1UEAwwSZDFkdnRsMTAwMC4xZGMuY29tAgEBMA0GCWCGSAFlAwQCAQUAoGkwGAYJKoZIhvcNAQkDMQsGCSqGSIb3DQEHATAcBgkqhkiG9w0BCQUxDxcNMTkwNjA3MTg0MTIxWjAvBgkqhkiG9w0BCQQxIgQg0PLaZU4YWZqtP9t/ygv9XIS/5ngU6FlGjpvyK6VFXVMwCgYIKoZIzj0EAwIERjBEAiBTNmQEPyc3aMm4Mwa0riD3dNdSc9aAhslj65Us8b3aKwIgNSc/y+CWpsr8qDln0fZK6ZD/LWPMxofQedlPy7Q6gY8AAAAAAAA=",</span></span></span>

<span><span><span>         "version":"EC_v1",</span></span></span>

<span><span><span>         "applicationData":"VEVTVA==",</span></span></span>

<span><span><span>         "merchantId":"merchant.com.fapi.tcoe.applepay"</span></span></span>

<span><span><span>      }</span></span></span>

<span><span><span>   },</span></span></span>

<span><span><span>   "transactionAmount":{</span></span></span>

<span><span><span>      "total":"12.99",</span></span></span>

<span><span><span>      "currency":"USD"</span></span></span>

<span><span><span>   }</span></span></span>

<span><span><span>}</span></span></span></pre>

<span><span><span><strong>Sample Apple Pay Response</strong></span></span></span>

<pre><span><span><span><span><span>{</span></span></span></span></span>

<span><span><span>   <span><span>"clientRequestId"</span></span><span><span>:</span></span><span><span>"741666"</span></span><span><span>,</span></span>
   <span><span>"apiTraceId"</span></span><span><span>:</span></span><span><span>"rrt-01b12ed35a0f32f98-c-ea-12855-958124-1"</span></span><span><span>,</span></span>
   <span><span>"ipgTransactionId"</span></span><span><span>:</span></span><span><span>"84290618651"</span></span><span><span>,</span></span>
   <span><span>"orderId"</span></span><span><span>:</span></span><span><span>"R-3f8d4c21-66c9-47d4-bb59-c7f167ace094"</span></span><span><span>,</span></span>
   <span><span>"transactionType"</span></span><span><span>:</span></span><span><span>"SALE"</span></span><span><span>,</span></span>
   <span><span>"transactionOrigin"</span></span><span><span>:</span></span><span><span>"ECOM"</span></span><span><span>,</span></span>
   <span><span>"paymentMethodDetails"</span></span><span><span>:</span></span><span><span>{</span></span></span></span></span>

<span><span><span>      <span><span>"expiryDate"</span></span><span><span>:</span></span><span><span>{</span></span></span></span></span>

<span><span><span>         <span><span>"month"</span></span><span><span>:</span></span><span><span>"**"</span></span><span><span>,</span></span>
         <span><span>"year"</span></span><span><span>:</span></span><span><span>"****"</span></span></span></span></span>

<span><span><span>      </span></span></span>

<span><span><span><span><span>}</span></span><span><span>,</span></span>
      <span><span>"bin"</span></span><span><span>:</span></span><span><span>"******"</span></span><span><span>,</span></span>
      <span><span>"last4"</span></span><span><span>:</span></span><span><span>"****"</span></span><span><span>,</span></span>
      <span><span>"brand"</span></span><span><span>:</span></span><span><span>"AMEX"</span></span></span></span></span>

<span><span><span>   </span></span></span>

<span><span><span><span><span>}</span></span><span><span>,</span></span>
   <span><span>"paymentMethodType"</span></span><span><span>:</span></span><span><span>"PAYMENT_CARD"</span></span><span><span>,</span></span>
   <span><span>"country"</span></span><span><span>:</span></span><span><span>"USA"</span></span><span><span>,</span></span>
   <span><span>"terminalId"</span></span><span><span>:</span></span><span><span>"1588390"</span></span><span><span>,</span></span>
   <span><span>"transactionTime"</span></span><span><span>:</span></span><span><span>1579707422</span></span><span><span>,</span></span>
   <span><span>"approvedAmount"</span></span><span><span>:</span></span><span><span>{</span></span></span></span></span>

<span><span><span>      <span><span>"total"</span></span><span><span>:</span></span><span><span>12.00</span></span><span><span>,</span></span>
      <span><span>"currency"</span></span><span><span>:</span></span><span><span>"USD"</span></span><span><span>,</span></span>
      <span><span>"components"</span></span><span><span>:</span></span><span><span>{</span></span></span></span></span>

<span><span><span>         <span><span>"subtotal"</span></span><span><span>:</span></span><span><span>12.00</span></span></span></span></span>

<span><span><span>      </span></span></span>

<span><span><span><span><span>}</span></span><span><span>,</span></span>
      <span><span>"transactionStatus"</span></span><span><span>:</span></span><span><span>"APPROVED"</span></span><span><span>,</span></span>
      <span><span>"schemeTransactionId"</span></span><span><span>:</span></span><span><span>"010022066071191"</span></span><span><span>,</span></span>
      <span><span>"processor"</span></span><span><span>:</span></span><span><span>{</span></span></span></span></span>

<span><span><span>         <span><span>"referenceNumber"</span></span><span><span>:</span></span><span><span>"84290618651 "</span></span><span><span>,</span></span>
         <span><span>"authorizationCode"</span></span><span><span>:</span></span><span><span>"OK4090"</span></span><span><span>,</span></span>
         <span><span>"responseCode"</span></span><span><span>:</span></span><span><span>"00"</span></span><span><span>,</span></span>
         <span><span>"network"</span></span><span><span>:</span></span><span><span>"AMEX"</span></span><span><span>,</span></span>
         <span><span>"associationResponseCode"</span></span><span><span>:</span></span><span><span>"000"</span></span><span><span>,</span></span>
         <span><span>"responseMessage"</span></span><span><span>:</span></span><span><span>"APPROVAL"</span></span><span><span>,</span></span>
         <span><span>"avsResponse"</span></span><span><span>:</span></span><span><span>{</span></span></span></span></span>

<span><span><span>            <span><span>"streetMatch"</span></span><span><span>:</span></span><span><span>"Y"</span></span><span><span>,</span></span>
            <span><span>"postalCodeMatch"</span></span><span><span>:</span></span><span><span>"Y"</span></span></span></span></span>

<span><span><span>         </span></span></span>

<span><span><span><span><span>}</span></span></span></span></span>

<span><span><span>      </span></span></span>

<span><span><span><span><span>}</span></span><span><span>,</span></span>
      <span><span>"additionalDetails"</span></span><span><span>:</span></span><span><span>{</span></span></span></span></span>

<span><span><span>         <span><span>"walletProvider"</span></span><span><span>:</span></span><span><span>"APPLE_PAY"</span></span></span></span></span>

<span><span><span>      </span></span></span>

<span><span><span><span><span>}</span></span></span></span></span>

<span><span><span>   </span></span></span>

<span><span><span><span><span>}</span></span></span></span></span>

<span><span><span><span><span><span>}</span></span></span></span></span></span></pre>

 [1]: https://support.apple.com/en-us/ht204916
