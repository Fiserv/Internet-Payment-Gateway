PayPal
---

<span><span><span>When integrating PayPal as a payment method, please refer to the following information.</span></span></span>

### **<span><span><span>Account Activation</span></span></span>**

<span><span><span><span><strong><span lang="EN-US"><span><span>Account Activation</span></span></span></strong></span></span></span></span>

  1. <span><span><span><span><span><span lang="EN-US"><span><span>If new to PayPal, create a new account via&nbsp;</span></span></span><span lang="EN-US"><span><span><a href="https://www.paypal.com/welcome/signup"><span><span><span>https://www.paypal.com/welcome/signup</span></span></span></a></span></span></span><span lang="EN-US"><span><span>, or reach out to PayPal directly to be guided through your setup.</span></span></span></span></span></span></span></span>
  2. <span><span><span><span><span><span lang="EN-US"><span><span><span>When you have a PayPal account you can&nbsp;log into your Virtual Terminal account and proceed to the ‘<em><span>Customization’&nbsp;</span></em>section to access the</span></span></span></span><span lang="DE"><span><span><span> ‘<em><span>PayPal Setup</span></em>’ page to </span></span></span></span><span lang="EN-US"><span><span>activate PayPal as a payment method in your store.</span></span></span></span></span></span></span></span>
  3. <span><span><span><span><span><span lang="EN-US"><span><span>After logging into your Virtual Terminal account, proceed to the ‘<em>Customization’&nbsp;</em>section to access the ‘<em>PayPal Setup</em>’ link, which leads you to the ‘<em>PayPal Setup</em>’ page.</span></span></span></span></span></span></span></span>
  4. <span><span><span><span><span><span lang="EN-US"><span><span>Once you land on this page </span></span></span><span lang="EN-US"><span><span><span>you have to configure&nbsp;your account details for processing PayPal transactions with the&nbsp;First Data Gateway:</span></span></span></span></span></span></span></span></span> 
      * <span><span><span><span><span><span><span lang="DE"><span>Allow guest checkout: Deactivate this checkbox if you do not want to allow your customers to use the PayPal payment method without a registered PayPal account.</span></span></span></span></span></span></span></span>
      * <span><span><span><span><span><span><span lang="EN-US"><span>PayPal header image (optional): Use this text field to determine the URL of an image (e. g. your logo) that shall be displayed on the PayPal site.</span></span></span></span></span></span></span></span>
      * <span><span><span><span><span><span><span lang="EN-US"><span>Custom colour (optional): Use this text field to determine the border colour (hex format) of the shopping cart box on the PayPal site.</span></span></span></span></span></span></span></span>
      * <span><span><span><span><span><span><span lang="EN-US"><span>Brand name (optional): Use this text field to determine the brand name that shall be shown on the PayPal site.</span></span></span></span></span></span></span></span>
      * <span><span><span><span><span><span><span lang="EN-US"><span>Account name (required): Use this text field to enter the registered email address (PayPal Business Seller Account Name) into ‘<em>Account Name</em>’. This must be unique for each store activated for you on First Data Gateway.</span></span></span></span></span></span></span></span>
      * <span><span><span><span><span><span><span lang="EN-US"><span>Permissions (required):click the ‘<em>Grant Permissions</em>’ button and select the relevant checkboxes in order to grant Third Party API Permissions for specific PayPal functionality that allows the First Data Gateway to contact PayPal and submit transactions on your behalf.</span></span></span></span></span></span></span></span>
  5. <span><span><span><span><span><span lang="EN-US"><span><span>You will then be redirected to the PayPal portal, where you must then log in and confirm granting the above permissions.</span></span></span></span></span></span></span></span>
  6. <span lang="EN-US"><span><span><span>Finally, you will be redirected to the ‘<em>PayPal Setup</em>’ page to receive confirmation that the activation process was successful.</span></span></span></span>

### &nbsp;

### **<span><span><span>Transaction Type Mapping</span></span></span>**

<table class="Table">
  <thead>
    <tr>
      <th>
        <p>
          <span><span><span>Gateway Transaction Type (txntype)</span></span></span>
        </p>
      </th>
      
      <th>
        <p>
          <span><span><span>PayPal Operation</span></span></span>
        </p>
      </th>
    </tr>
  </thead>
  
  <tbody>
    <tr>
      <td>
        <p>
          <span><span><span>sale</span></span></span>
        </p>
      </td>
      
      <td>
        <p>
          <span><span><span>SetExpressCheckoutPayment (<em>sets ‘PaymentAction’ to ‘Authorization’ in ‘SetExpressCheckout’ and ‘DoExpressCheckoutPayment’ requests)</em></span></span></span>
        </p>
      </td>
    </tr>
    
    <tr>
      <td>
        <p>
          <span><span><span>preauth</span></span></span>
        </p>
      </td>
      
      <td>
        <p>
          <span><span><span>GetExpressCheckoutDetails</span></span></span>
        </p>
      </td>
    </tr>
    
    <tr>
      <td>
        <p>
          <span><span><span>sale – with additional parameters for installing a Recurring Payment</span></span></span>
        </p>
      </td>
      
      <td>
        <p>
          <span><span><span>DoExpressCheckoutPayment*</span></span></span>
        </p>
      </td>
    </tr>
    
    <tr>
      <td>
        <p>
          <span><span><span>postauth</span></span></span>
        </p>
      </td>
      
      <td>
        <p>
          <span><span><span>DoCapture (<em>,DoReauthorization</em>)</span></span></span>
        </p>
      </td>
    </tr>
    
    <tr>
      <td>
        <p>
          <span><span><span>void</span></span></span>
        </p>
      </td>
      
      <td>
        <p>
          <span><span><span>DoVoid</span></span></span>
        </p>
      </td>
    </tr>
  </tbody>
</table>

<span><span><span>*To use PayPal’s Reference Transaction feature for Recurring Payments, please contact PayPal beforehand to verify your PayPal account meets the necessary requirements for this feature.</span></span></span>  
&nbsp;

### &nbsp;

### **<span><span><span>Address Handling</span></span></span>**

<span><span><span>If you pass a full set of <a href="https://docs.firstdata.com/org/gateway/node/212">address values</a> with your request, these values are forwarded to PayPal. This sets the PayPal parameter ‘addressOverride’ to ‘1’.</span></span></span>

<span><span><span>NOTE: It is an eligibility requirement for PayPal’s Seller Protection that the shipping address is submitted to PayPal. If you do not submit, or submit an incomplete address, no data will be forwarded to PayPal and the parameter ‘addressOverride’ will not be set.</span></span></span>

<span><span><span>Regardless of the logic outlined above, the payment gateway will always store the ‘shipTo’ address fields received from PayPal in the ‘GetDetails’ request in the ‘ShippingAddress’ fields. These fields may overwrite values passed in the request, depending on the above logic.</span></span></span>
