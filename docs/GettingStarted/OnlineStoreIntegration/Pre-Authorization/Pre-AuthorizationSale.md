---
title: Pre-Authorization/Sale
author: steffen.dangel@firstdata.de
---

## Step 1: Checkout Process in Your Webstore

The easiest first step for adding payments capabilities to your website is to implement a HTTP form that you post to our Gateway URL.

This type of integration allows you to let our Gateway manage the customer redirections that are required in the checkout process of many payment methods or authentication mechanisms and gives you the option to use&nbsp; secure hosted pages or an embeddable form which can reduce the burden of compliance with the Data Security Standard of the Payment Card Industry (PCI DSS).

With the transaction type **Pre-Authorization** (_preauth_) you can reserve funds on a customer's card account. This transaction does not charge the card until you perform a [Completion][1] transaction. Note that authorizations reserve funds for varying periods, depending on the issuing card company's policy. We strongly suggest that you confirm shipment as soon as possible after authorization.

Alternatively you can use the transaction type **Sale** (_sale_) which immediately charges a customer’s card or bank account over night with no further action required from you.

##### Alternative Options

> [Check out our API documentation][2]

&nbsp;

### What You Need

  * Store Name (_storename_)  
    This is the ID of the store that was given to you by First Data. For example : 10123456789  
    &nbsp;
  * Shared Secret  
    This is the shared secret provided to you by First Data. This is used when [constructing the hash value][3].  
    &nbsp;

### URL for Test Transactions

<pre><span><span><span><span><span><span>https://test.ipg-online.com/connect/gateway/processing</span></span></span></span></span></span></pre>

<span><span><span><span>You will get the production URL with your production account credentials.</span></span></span></span>

&nbsp;

### Building the Request

<span><span><span><span>Independently of the payment method, there are some mandatory fields that need to be included in your transaction request:</span></span></span></span>

<table>
  <tbody>
    <tr>
      <td>
        <p>
          <strong><span><span><span><span><span><span><span>Field</span></span></span></span></span></span></span></strong>
        </p>
      </td>
      
      <td>
        &nbsp;&nbsp;
      </td>
      
      <td>
        <p>
          <strong><span><span><span><span><span><span><span>Comment</span></span></span></span></span></span></span></strong>
        </p>
      </td>
    </tr>
    
    <tr>
      <td>
        <p>
          <span><span><span><span><span>txntype</span></span></span></span></span>
        </p>
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        <p>
          <span><span><span><span>The type of the transaction<em>: </em></span></span></span></span><em>preauth, sale</em> or <em>payer_auth </em>(see info on <em>payer_auth</em> <a href="http://test-ndpfdc.pantheonsite.io/org/gateway/node/95">here</a>)
        </p>
      </td>
    </tr>
    
    <tr>
      <td>
        <p>
          <span><span><span><span><span>timezone</span></span></span></span></span>
        </p>
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        <p>
          <span><span><span><span>The timezone of the transaction in Area/Location format,<br /> e.g. </span><em><span><span>America/New_York</span></span></em><span>&nbsp; or </span><em><span><span>Europe/Berlin</span></span></em></span></span></span>
        </p>
      </td>
    </tr>
    
    <tr>
      <td>
        <p>
          <span><span><span><span><span>txndatetime</span></span></span></span></span>
        </p>
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        <p>
          <span><span><span><span>The exact time of the transaction in format<br /> YYYY:MM:DD-hh:mm:ss</span></span></span></span>
        </p>
      </td>
    </tr>
    
    <tr>
      <td>
        <p>
          <span><span><span><span><span>hash_algorithm</span></span></span></span></span>
        </p>
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        <p>
          <span><span><span><span>This is to indicate the algorithm that you use for hash calculation. Valid values are </span><span><span><em>SHA256 </em>or <em>SHA512</em>.</span></span></span></span></span>
        </p>
      </td>
    </tr>
    
    <tr>
      <td>
        <p>
          <span><span><span><span><span>hash</span></span></span></span></span>
        </p>
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        <p>
          <span><span><span><span>This is a <a href="http://test-ndpfdc.pantheonsite.io/org/gateway/node/58">SHA hash</a> of the following fields: </span><span><span>storename</span></span><span> + </span><span><span>txndatetime</span></span><span> + </span><span><span>chargetotal</span></span><span> + </span><span><span>currency</span></span><span> + </span><span><span>sharedsecret.</span></span></span></span></span>
        </p>
        
        <p>
          <span><span><span><span>Note that it is important to have the hash generated in this exact order.<br /> <br /> As an optional security feature, you can instead include all parameters of the transaction request in the parameter </span><em><span><span>hashExtended</span></span></em><span>. It needs to be calculated using all request parameters in ascending order of the parameter names.</span></span></span></span>
        </p>
      </td>
    </tr>
    
    <tr>
      <td>
        <p>
          <span><span><span><span><span>storename</span></span></span></span></span>
        </p>
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        <p>
          <span><span><span><span>The ID of the store provided to you by First Data, e.g. </span><span><span>541234567</span></span></span></span></span>
        </p>
      </td>
    </tr>
    
    <tr>
      <td>
        <p>
          <span><span><span><span><span>chargetotal</span></span></span></span></span>
        </p>
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        <p>
          <span><span><span><span>The total amount of the transaction using a dot or comma as decimal separator, e.g. </span><span><span>12.34</span></span><span> for an amount of 12 Dollar and 34 Cents. Group separators like1,000.01 / 1.000,01 are not allowed.</span></span></span></span>
        </p>
      </td>
    </tr>
    
    <tr>
      <td>
        <p>
          <span><span><span><span><span>currency</span></span></span></span></span>
        </p>
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        <p>
          <span><span><span><span>The numeric ISO code of the <a href="http://test-ndpfdc.pantheonsite.io/org/gateway/node/56">transaction currency</a>,<br /> e. g. </span><span><span>840</span></span><span> for US Dollar or </span><span><span>978</span></span><span> for Euro</span></span></span></span>
        </p>
      </td>
    </tr>
  </tbody>
</table>

### &nbsp;

### Sample Code for Your Checkout Form

<span>Example of a form with the minimum number of fields:</span>

<pre>&lt;form method="post" action="https://test.ipg-online.com/connect/gateway/processing "&gt;
&lt;input type="hidden" name="txntype" value="preauth"&gt;
&lt;input type="hidden" name="timezone" value="Europe/Berlin"/&gt;
&lt;input type="hidden" name="txndatetime" value="&lt;% getDateTime() %&gt;"/&gt;
&lt;input type="hidden” name="hash_algorithm" value="SHA256"/&gt;
&lt;input type="hidden" name="hash" value="&lt;% call createHash( "13.00","978" ) %&gt;"/&gt;
&lt;input type="hidden" name="storename" value="10123456789" /&gt;
&lt;input type="text" name="chargetotal" value="13.00" /&gt;
&lt;input type="hidden" name="currency" value="978"/&gt;
&lt;input type="submit" value="Submit"&gt;
&lt;/form&gt;</pre>

> [How to Generate the SHA-256 Hash][3]  
> [Values for defining the payment method][4]  
> [Parameters for billing/shipping information][5]

## &nbsp;

## Next Steps

> [Transaction Response][6]  
> [Completion (Post-Authorization)][1]  
> [Void][7]  
> [Return][8]

 [1]: http://test-ndpfdc.pantheonsite.io/org/gateway/node/318
 [2]: http://test-ndpfdc.pantheonsite.io/org/gateway/docs/api
 [3]: http://test-ndpfdc.pantheonsite.io/org/gateway/node/58
 [4]: http://test-ndpfdc.pantheonsite.io/org/gateway/node/55
 [5]: http://test-ndpfdc.pantheonsite.io/org/gateway/node/212
 [6]: http://test-ndpfdc.pantheonsite.io/org/gateway/node/315
 [7]: http://test-ndpfdc.pantheonsite.io/org/gateway/node/319
 [8]: http://test-ndpfdc.pantheonsite.io/org/gateway/node/223
