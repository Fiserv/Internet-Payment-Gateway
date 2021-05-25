<p class="CxSpFirst">
  <span><span><span><span><span>Using Direct Post allows you to have full control over the look and feel of the form where your customers enter their card details for&nbsp;payment while simultaneously avoiding the need to have sensitive card data within your systems.</span></span></span></span></span>
</p>

<p class="CxSpFirst">
  You create the payment form and display it within your website or app. When your customer has entered the card details and presses the "continue button", the customer's device sends the payment information directly to Fiserv.
</p>

<img alt="directpost-option" data-align="center" data-entity-type="file" data-entity-uuid="062c1304-eab1-40e2-8667-856ec2e7d358" src="/files/directpost-option.png" /> 

<p class="CxSpFirst">
  <span><span><span><span><span>This comes with many advantages and benefits to you with regard to both the customer experience, and your overall <a href="https://www.pcisecuritystandards.org/">PCI Data Security Standard</a> compliance exposure.</span></span></span></span></span>
</p>

<span><span><span><span><span>If you choose the Direct Post option and create your own forms, there are additional fields that must be included in your transaction requests. The available options are listed below. It is also important that you check that JavaScript is enabled in your customer’s browser. If necessary, inform your customer that JavaScript needs to be enabled for the payment process.</span></span></span></span></span>

### &nbsp;

### <span><span><span>Required Fields</span></span></span>

<p class="CxSpMiddle">
  <span><span><span>After your customer has decided on his/her payment method, you present a corresponding HTML-page with a form to enter the payment data as well as hidden parameters containing additional transaction information. In addition to any <a href="https://docs.firstdata.com/org/gateway/node/321">mandatory fields</a>, your form must contain the following fields (some of which can be hidden) to&nbsp;use&nbsp;the Direct Post option:</span></span></span>
</p>

<table class="Table">
  <thead>
    <tr>
      <th>
        <p>
          <span><span><span><span>Field</span></span></span></span>
        </p>
      </th>
      
      <th>
        &nbsp;
      </th>
      
      <th>
        <p>
          <span><span><span><span>Comment</span></span></span></span>
        </p>
      </th>
    </tr>
    
    <tr>
      <td>
        <p>
          paymentMethod
        </p>
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        <p>
          If you let the customer select the payment method (e. g. MasterCard, Visa, Direct Debit) in your shop environment or want to define the payment type yourself, transmit the parameter ‘paymentMethod’ along with your Sale or PreAuth transaction.<br /> If you do not submit this parameter, the payment gateway will display a drop-down menu to the customer to choose from the payment methods available for your shop.
        </p>
        
        <p>
          > <a href="http://docs.firstdata.com/org/gateway/node/55">See valid values here</a>
        </p>
      </td>
    </tr>
    
    <tr>
      <td>
        responseFailURL
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        The URL where you wish to direct customers after a declined or unsuccessful transaction (your Sorry URL) – only needed if not setup in Virtual Terminal / Customization.
      </td>
    </tr>
    
    <tr>
      <td>
        responseSuccessURL
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        The URL where you wish to direct customers after a successful transaction (your Thank You URL) – only needed if not setup in Virtual Terminal / Customization.
      </td>
    </tr>
  </thead>
</table>

#### &nbsp;

#### For Credit/Debit Card Details

<table class="Table">
  <thead>
    <tr>
      <th>
        <p>
          <span><span><span><span>Field</span></span></span></span>
        </p>
      </th>
      
      <th>
        &nbsp;
      </th>
      
      <th>
        <p>
          Comment
        </p>
      </th>
    </tr>
  </thead>
  
  <tbody>
    <tr>
      <td>
        <p>
          <span><span><span><span>cardnumber</span></span></span></span>
        </p>
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        <p>
          <span><span><span><span>Your customer’s card number (12-24 digits)</span></span></span></span>
        </p>
      </td>
    </tr>
    
    <tr>
      <td>
        <p>
          <span><span><span><span>expmonth </span></span></span></span>
        </p>
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        <p>
          <span><span><span><span>Card expiry month (2 digits) </span><em><span><span>(mandatory if credit card)</span></span></em></span></span></span>
        </p>
      </td>
    </tr>
    
    <tr>
      <td>
        <p>
          <span><span><span><span>expyear </span></span></span></span>
        </p>
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        <p>
          <span><span><span><span>Card expiry year (4 digits) </span><em><span><span>(mandatory if credit card)</span></span></em></span></span></span>
        </p>
      </td>
    </tr>
    
    <tr>
      <td>
        <p>
          <span><span><span><span>cvm </span></span></span></span>
        </p>
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        <p>
          <span><span><span><span>Card code, usually back of the card (3/4 digits) </span><em><span><span>(mandatory if credit card) (optional “if on card”) (not needed for Bancontact)</span></span></em></span></span></span>
        </p>
      </td>
    </tr>
  </tbody>
</table>

<p class="CxSpMiddle">
  &nbsp;
</p>

<h4 class="CxSpMiddle">
  For SEPA Direct Debit Details
</h4>

<table class="Table">
  <thead>
    <tr>
      <th>
        <p>
          <span><span><span><span>Field</span></span></span></span>
        </p>
      </th>
      
      <th>
        &nbsp;
      </th>
      
      <th>
        <p>
          <span><span><span><span>Comment</span></span></span></span>
        </p>
      </th>
    </tr>
  </thead>
  
  <tbody>
    <tr>
      <td>
        <p>
          <span><span><span><span>iban</span></span></span></span>
        </p>
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        <p>
          <span><span><span><span>International bank account number (22 digits)</span></span></span></span>
        </p>
      </td>
    </tr>
    
    <tr>
      <td>
        <p>
          <span><span><span><span>bic </span></span></span></span>
        </p>
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        <p>
          <span><span><span><span>Business identifier code (8/11 digits) </span><em><span><span>(mandatory if foreign IBAN)</span></span></em></span></span></span>
        </p>
      </td>
    </tr>
    
    <tr>
      <td>
        <p>
          <span><span><span><span>bname</span></span></span></span>
        </p>
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        <p>
          <span><span><span><span>Name of bank account owner</span></span></span></span>
        </p>
      </td>
    </tr>
  </tbody>
</table>

<p class="CxSpMiddle">
  &nbsp;
</p>

<p class="CxSpMiddle">
  <span><span><span>You can also transfer <a href="https://docs.firstdata.com/org/gateway/node/212">billing and shipping</a>&nbsp;information to First Data Gateway.</span></span></span>
</p>

<p class="CxSpMiddle">
  <span><span><span>> <a href="https://docs.firstdata.com/org/gateway/node/224">See other optional fields that might be useful for your business </a></span></span></span>
</p>

<p class="CxSpMiddle">
  &nbsp;
</p>

<h3 class="CxSpMiddle">
  <span><span><span>Validity Checks</span></span></span>
</h3>

<span><span><span><span><span>Prior to the authorization request for transactions, the First Data Gateway performs the following validation checks:</span></span></span></span></span>

<li class="CxSpMiddle">
  <span><span><span>Expiry date of the cards must be in the future</span></span></span>
</li>
<li class="CxSpMiddle">
  <span><span><span>Card security codes must contain 3 or 4 digits</span></span></span>
</li>
<li class="CxSpMiddle">
  <span><span><span>Structure of the card number must be correct</span></span></span>
</li>
<li class="CxSpMiddle">
  <span><span><span>IBAN for Direct Debit transactions must contain 22 digits</span></span></span>
</li>
<li class="CxSpMiddle">
  <span><span><span>BIC for Direct Debit transactions must contain 8 or 11 digits</span></span></span>
</li>

<span><span><span><span><span>If the submitted data is invalid, the First Data Gateway would usually send a corresponding data entry page to the customer. However, using the silent post feature, you can transmit an additional parameter along with transaction data: ‘full_bypass=true’. In this case, you get the result of the validity check back in the transaction response and can display your own error page.</span></span></span></span></span>

&nbsp;

### Sample Code for the HTML Form

<pre><span><span><span><span><span>&lt;form method="post" action="https://test.ipg-online.com/connect/gateway/processing"&gt;
</span></span></span></span></span>
<span lang="SK"><span>&lt;!-- Hidden fields to be prefilled by the merchant --&gt;&nbsp;&nbsp; </span></span>
<span><span><span><span><span>   &lt;input type="hidden" name="full_bypass" value="true"&gt;</span></span></span></span></span>
<span><span><span><span><span>   &lt;input type="hidden" name="txntype" value="sale"&gt;</span></span></span></span></span>
<span><span><span><span><span>   &lt;input type="hidden" name="paymentMethod" value="V"&gt;</span></span></span></span></span>
<span><span><span><span><span>   &lt;input type="hidden" name="timezone" value="Europe/Berlin"&gt;</span></span></span></span></span>
<span><span><span><span><span>   &lt;input type="hidden" name="txndatetime" value="&lt;?php echo getDateTime() ?&gt;"&gt;</span></span></span></span></span>
<span><span><span><span><span>   &lt;input type="hidden" name="hash_algorithm" value="HMACSHA256"&gt;</span></span></span></span></span>
   <span><span><span><span><span>&lt;input type="hidden" name="hashExtended" value="&lt;?php echo createExtendedHash( "13.00","978" ) ?&gt;"&gt;</span></span></span></span></span>
   <span><span><span><span><span>&lt;input type="hidden" name="storename" value="10123456789"&gt;</span></span></span></span></span>
   <span><span><span><span><span>&lt;input type="hidden" name="chargetotal" value="13.00"&gt;</span></span></span></span></span>
   <span><span><span><span><span>&lt;input type="hidden" name="currency" value="978"&gt;
   </span></span></span></span></span><span><span><span><span><span>&lt;input type="hidden" name="language" value="en_US"&gt;</span></span></span></span></span>

<span lang="SK">&lt;!-- Fields to be entered by the cardholder --&gt;</span>
<span lang="SK"> &lt;div&gt;</span>
<span lang="SK">   &lt;!-- credit card number: e.g. 4111111111111111 --&gt;</span>
<span lang="SK">   &lt;label for="cardnumber"&gt;Card Number:&lt;/label&gt;</span>
<span lang="SK">   &lt;input type="text" name="cardnumber" id="cardnumber"&gt;
</span><span lang="SK"> &lt;/div&gt;</span>

<span lang="SK"> &lt;div&gt;</span>
<span lang="SK">   &lt;!-- expiration month of the card: e.g. 07 --&gt;&nbsp;&nbsp; </span>
<span lang="SK">   &lt;label for="expmonth"&gt;Expiration Month:&lt;/label&gt;
</span><span lang="SK">   &lt;input type="text" name="expmonth" id="expmonth"&gt;</span>
<span lang="SK"> &lt;/div&gt;</span>

<span lang="SK"> &lt;div&gt;</span>
<span lang="SK">   &lt;!-- expiration year of the card: e.g. 2024 --&gt;</span>
<span lang="SK">   &lt;label for="expyear"&gt;Expiration Year:&lt;/label&gt;
</span><span lang="SK">   &lt;input type="text" name="expyear" id="expyear"&gt;</span>
<span lang="SK"> &lt;/div&gt;</span>

<span lang="SK"> &lt;div&gt;</span>
<span lang="SK">   &lt;!-- card security code (CVV/CVC): e.g. 123 --&gt;</span>
<span lang="SK">   &lt;label for="cvm"&gt;Security Code:&lt;/label&gt;
   </span><span lang="SK">&lt;input type="text" name="cvm" id="cvm"&gt;</span>
<span lang="SK"> &lt;/div&gt;</span>

<span lang="SK"> &lt;div&gt;</span>
<span lang="SK">   &lt;input type="submit" value="Submit"&gt;Pay now&lt;/input&gt;</span>
<span lang="SK"> &lt;/div&gt;

</span><span lang="SK">&lt;/form&gt;</span>
</pre>
