---
title: 3-D Secure 
author: adriana.vas@firstdata.de
---

<span>3-D Secure authentication provides an additional security layer for online card transactions. </span>

<span>If your merchant account is enabled for 3-D Secure, all <em>sale </em>or <em>preauth </em>transactions that you initiate by posting an HTML form will by default go through the 3-D Secure process without the need for you to do anything, i.e. cardholders with an enrolled card will see a page from the card issuer to enter the password unless the card issuer decides not to check it.</span>

<span>After the authentication, we bring the cardholder back to your webstore.</span>

&nbsp;

##### Alternative Options

[> Check out how to use 3-D Secure in an API scenario][1]

[> Split Authentication and Authorization into two steps][2] 

&nbsp;

### 3-D Secure Specifics in the Transaction Response

<span><span><span lang="EN-GB">Upon completion, the transaction details will be sent back to the defined <em>responseSuccessURL</em> or <em>responseFailURL</em> as hidden fields.</span></span></span>

<span><span><span lang="EN-GB">Return code indicating the classification of the transaction:</span></span></span>

<span><span><span lang="EN-GB"><strong>1</strong> – Successful authentication (VISA ECI 05, MasterCard ECI 02)</span></span></span>

<span><span><span lang="EN-GB"><strong>2</strong> – Successful authentication without AVV (VISA ECI 05, MasterCard ECI 02)</span></span></span>

<span><span><span lang="EN-GB"><strong>3</strong> – Authentication failed / incorrect password (transaction declined)</span></span></span>

<span><span><span lang="EN-GB"><strong>4</strong> – Authentication attempt (VISA ECI 06, MasterCard ECI 01)</span></span></span>

<span><span><span lang="EN-GB"><strong>5</strong> – Unable to authenticate / Directory Server not responding (VISA ECI 07)</span></span></span>

<span><span><span lang="EN-GB"><strong>6</strong> – Unable to authenticate / Access Control Server not responding (VISA ECI 07)</span></span></span>

<span><span><span lang="EN-GB"><strong>7</strong> – Cardholder not enrolled for 3-D Secure (VISA ECI 06)</span></span></span>

<span><span><span lang="EN-GB"><strong>8</strong> – Invalid 3-D Secure values received, most likely by the credit card issuing bank’s Access Control Server (ACS)</span></span></span>

&nbsp;

### <span>Enabling/Disabling 3-D Secure on a Transaction-by-Transaction Basis</span>

<span>The optional parameter <em>authenticateTransaction</em></span> <span></span><span>can be used in case you want to send specific transactions without 3-D Secure.</span>

&nbsp;

**<span><span><span lang="EN-GB">Example for a transaction with&nbsp;3-D Secure:</span></span></span>**

<pre><span><span><span lang="EN-GB"><span>&lt;input type="hidden" name="authenticateTransaction" value="true"/&gt;</span></span></span></span></pre>

&nbsp;

**<span><span><span lang="EN-GB">Example for a transaction without 3-D Secure:</span></span></span>**

<pre><span><span><span lang="EN-GB"><span>&lt;input type="hidden" name="authenticateTransaction" value="false"/&gt;</span></span></span></span></pre>

&nbsp;

### Additional Information

  * <span><span><span lang="EN-GB">In principle, it may occur that 3-D Secure authentications cannot be processed successfully for technical reasons.</span></span></span> <span><span><span lang="EN-GB">If one of the systems involved in the authentication process is temporarily not responding, the payment transaction will be processed as a “regular” eCommerce transaction (ECI 7). <strong>A liability shift to the card issuer for possible chargebacks is not warranted in this case</strong>. If you prefer that such transactions shall not be processed at all, our technical support teams can block them for your Store on request.</span></span></span>  
    &nbsp;
  * <span><span><span lang="EN-GB">Credit card transactions with 3-D Secure hold in a pending status while cardholders search for their password or need to activate their card for 3-D Secure during their shopping experience. During this time when the final transaction result of the transaction is not yet determined, the payment gateway sets the Approval Code to „?:waiting 3dsecure“. If the session expires before the cardholder returns from the 3-D Secure dialogue with his bank, the transaction will be shown as “N:-5103:Cardholder did not return from ACS”.</span></span></span>  
    &nbsp;
  * <span><span><span lang="EN-GB">Please note that the technical process of 3D Secure transactions differs in some points compared to a normal transaction flow. If you already have an existing shop integration and plan to activate 3D Secure subsequently, we recommend performing some test transactions on our test environment.</span></span></span>

 [1]: http://test-ndpfdc.pantheonsite.io/org/gateway/docs/api
 [2]: http://test-ndpfdc.pantheonsite.io/org/gateway/node/95
