### Pre-Authorization/Sale
---

## Step 1: Checkout Process in Your Webstore

The easiest first step for adding payments capabilities to your website is to implement a HTML form that you post to our Gateway URL.

This type of integration allows you to let our Gateway manage the customer redirections that are required in the checkout process of many payment methods or authentication mechanisms and gives you the option to use&nbsp;secure hosted pages or an embeddable form which can reduce the burden of compliance with the Data Security Standard of the Payment Card Industry (PCI DSS).

With the transaction type **Pre-Authorization** (_preauth_) you can reserve funds on a customer's card account. This transaction does not charge the card until you perform a [Completion][1] transaction. Note that pre-authorizations reserve funds for varying periods, depending on the issuing card company's policy. We strongly suggest that you confirm shipment as soon as possible after authorization.

Alternatively you can use the transaction type **Sale** (_sale_) which immediately charges a customer’s card or bank account over night with no further action required from you.

&nbsp;

### Integration Options

  * Fully outsource the payment process using [Hosted Payment Pages][2]
  * Full control over the look and feel using a [Direct Post][3]

##### Alternative Options

> [API-only&nbsp;][4][integration][5]  
> [Tokenize card details with JavaScript][6]

&nbsp;

### What You Need

When using the [Direct Post][3]&nbsp;or&nbsp;[Hosted Payment Pages][2]&nbsp;options, you need:

  * Store Name (_storename_)  
    This is the ID of the store that was given to you by First Data. For example : 10123456789  
    &nbsp;
  * Shared Secret  
    This is the shared secret provided to you by First Data. This is used when [constructing the hash value][7].  
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
          <span><span><span><span>The type of the transaction<em>: </em></span></span></span></span><em>preauth, sale</em> or <em>payer_auth </em>(see info on <em>payer_auth</em> <a href="http://docs.firstdata.com/org/gateway/node/95">here</a>)
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
          <span><span><span><span>This is to indicate the algorithm that you use for hash calculation. Valid values are:&nbsp;<em>HMACSHA256</em> or <em>HMACSHA384</em> or&nbsp;<em>HMACSHA512</em></span></span></span></span>
        </p>
      </td>
    </tr>
    
    <tr>
      <td>
        <p>
          <span><span><span><span><span>hash</span></span></span></span></span><span lang="EN-US"><span>Extended </span></span>
        </p>
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        <p>
          <span><span><span><span>The extended hash needs to be calculated using all request parameters in ascending order of the parameter names.<br /> When you are using Direct Post, there is also an option where you do not need to know the card details (PAN, CVV and Expiry Date) for the hash calculation. This will be managed with a specific setting performed on your store. Please contact your local support team if you want to enable this feature.</span></span></span></span>
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
          <span><span><span><span>The total amount of the transaction using a dot or comma as decimal separator, e.g. </span><span><span>12.34</span></span><span> for an amount of 12 Dollar and 34 Cents. Group separators like 1,000.01 / 1.000,01 are not allowed.</span></span></span></span>
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
          <span><span><span><span>The numeric ISO code of the <a href="http://docs.firstdata.com/org/gateway/node/56">transaction currency</a>,<br /> e.g. </span><span><span>840</span></span><span> for US Dollar or </span><span><span>978</span></span><span> for Euro</span></span></span></span>
        </p>
      </td>
    </tr>
  </tbody>
</table>

### &nbsp;

### Sample Code for Your Checkout Form

<span>Example of a form with the minimum number of fields:</span>

<pre>&lt;form method="post" action="https://test.ipg-online.com/connect/gateway/processing"&gt;
  &lt;input type="hidden" name="txntype" value="preauth"&gt;
  &lt;input type="hidden" name="timezone" value="Europe/Berlin"&gt;
<span><span><span><span><span>  </span></span></span></span></span><span><span><span><span><span>&lt;input type="hidden" name="txndatetime" value="&lt;% getDateTime() %&gt;"/&gt;
  &lt;input type="hidden" name="hash_algorithm" value="HMACSHA256"/&gt;
  &lt;input type="hidden" name="hashExtended" value="&lt;% call createExtendedHash( "13.00","978" ) %&gt;"/&gt;
  </span></span></span></span></span>&lt;input type="hidden" name="storename" value="10123456789"&gt;
  &lt;input type="text" name="chargetotal" value="13.00"&gt;
  &lt;input type="hidden" name="currency" value="978"&gt;
  &lt;input type="submit" value="Submit"&gt;
&lt;/form&gt;</pre>

> [How to generate a&nbsp;hash][7]  
> [Values for defining the payment method][8]  
> [Parameters for billing/shipping information][9]

### &nbsp;

## Next Steps

> [Transaction Response][10]  
> [Completion (Post-Authorization)][1]  
> [Void][11]  
> [Return][12]

 [1]: http://docs.firstdata.com/org/gateway/node/318
 [2]: https://docs.firstdata.com/org/gateway/node/316
 [3]: https://docs.firstdata.com/org/gateway/node/350
 [4]: http://docs.firstdata.com/org/gateway/docs/api
 [5]: https://docs.firstdata.com/org/gateway/node/326
 [6]: https://docs.firstdata.com/org/gateway/node/1040
 [7]: http://docs.firstdata.com/org/gateway/node/58
 [8]: http://docs.firstdata.com/org/gateway/node/55
 [9]: http://docs.firstdata.com/org/gateway/node/212
 [10]: http://docs.firstdata.com/org/gateway/node/315
 [11]: http://docs.firstdata.com/org/gateway/node/319
 [12]: http://docs.firstdata.com/org/gateway/node/223
