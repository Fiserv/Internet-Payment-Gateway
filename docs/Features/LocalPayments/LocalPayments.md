Local Payments
---

_The following information is only relevant if you are using Fiserv's Local Payments solution._

A Sale transaction for most Local Payments requires a direct interaction with the consumer who needs to be redirected to the payment method’s screens (e.g. the login page of the consumer’s bank or a wallet provider) and back to your website after all required steps are completed.

As we handle all the required redirections to the various stakeholders for you, all you need to do is to post a form to a URL with the parameters and values required for the transaction.

> [See how to intiate a transaction using a HTML form that you post to our Gateway URL][1]

&nbsp;

### Specific Fields to be Considered for Local Payments

<table>
  <tbody>
    <tr>
      <td>
        <strong>Field Name</strong>
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        <strong><span lang="EN-US"><span>Description</span></span></strong>
      </td>
      
      <td>
        &nbsp;
      </td>
    </tr>
    
    <tr>
      <td>
        <pre>
checkoutoption</pre>
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        <span lang="EN-US"><span>Set the value for this parameter to </span></span><span lang="EN-US"><span>‘combinedpage’ for a payment process where the payment method choice and the typical next step (e.g. entry of card details or selection of bank) in consolidated in a single page</span></span>
      </td>
      
      <td>
        &nbsp;
      </td>
    </tr>
    
    <tr>
      <td>
        <pre>
paymentMethod</pre>
      </td>
      
      <td>
        &nbsp;&nbsp;
      </td>
      
      <td>
        You can submit the parameter <em>paymentMethod</em> in your transaction request to determine the payment method to be used for the transaction. See possible values <a href="http://docs.firstdata.com/org/gateway/node/55">here</a>.<br /> If you do not submit this parameter, the Gateway will display a page to your consumer to choose from the payment methods that are supported for the combination of the consumer’s country and the transaction currency.
      </td>
      
      <td>
        &nbsp;
      </td>
    </tr>
    
    <tr>
      <td>
        <pre>
bname</pre>
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        The consumer’s name, e.g. Albert Einstein. This is required for all Local Payments transactions. If you do not submit this field, a hosted page will be displayed to the consumer to capture the name.
      </td>
      
      <td>
        &nbsp;
      </td>
    </tr>
    
    <tr>
      <td>
        <pre>
bcountry</pre>
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        The consumer’s country in Two Letter Country Code format, e.g. US for the United States or DE for Germany. The country is required for many Local Payments methods so we recommend to include it in every Sale transaction request. If you do not submit this field and the payment method requires it, a hosted page will be displayed with the country that we have identified based on IP address and the option to change the country if not appropriate.
      </td>
      
      <td>
        &nbsp;
      </td>
    </tr>
  </tbody>
</table>

<span lang="EN-US">Many of the payment methods are available for customers coming from a certain country. In the scenarios where you use the hosted payment page for payment selection, the gateway can display to your consumers a hosted page with only these payment methods that are set up for your store and supported for the combination of the consumer’s country and the transaction currency. This validation is done either based on the submitted billing country (‘bcountry’) or the customer’s IP address.&nbsp;</span>

<span lang="EN-US">See below an example of a hosted payment page in the checkout option ‘combinedpage’, where the country is pre-set to ‘Germany’ based on the customer’s IP address but still it can be changed via a dedicated drop-down, where else the payment methods are limited based on the combination country/currency.</span>

<img alt="eg" data-align="center" data-entity-type="file" data-entity-uuid="39e5233a-feed-4ffc-bc4b-717c835c7889" height="361" src="/files/connectup1.png" width="566" /> 

### Payment Method Specific Fields to be Considered for Local Payments

(M)=Mandatory&nbsp;(O)=Optional

<table>
  <tbody>
    <tr>
      <td>
        <strong>Field Name</strong>
      </td>
      
      <td>
        <strong>Relevant for </strong>
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        <span lang="EN-US"><span><strong>Description</strong></span></span>
      </td>
    </tr>
    
    <tr>
      <td>
        <pre>
nationalId</pre>
      </td>
      
      <td>
        <p>
          Boleto Bancário (M) Santander (M) Santander Cash (M)<br /> Trustly (O)
        </p>
      </td>
      
      <td>
        &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;
      </td>
      
      <td>
        Consumer’s National ID (up to 30 characters)
      </td>
    </tr>
    
    <tr>
      <td>
        <pre>
customerid</pre>
      </td>
      
      <td>
        Boleto Bancário (M)<br /> Santander (M)<br /> Santander Cash (M)<br /> Trustly (M)
      </td>
      
      <td>
        &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;&nbsp;
      </td>
      
      <td>
        Unique reference to identify the consumer
      </td>
    </tr>
    
    <tr>
      <td>
        <pre>
email</pre>
      </td>
      
      <td>
        Boleto Bancário (M)<br /> Przelewy24 (P24) (M)<br /> SEPA Direct Debit (M)<br /> Santander (M)<br /> Santander Cash (M)
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        Consumer’s email address
      </td>
    </tr>
    
    <tr>
      <td>
        <pre>
bbirthday</pre>
      </td>
      
      <td>
        Boleto Bancário (O)<br /> Santander (O)<br /> Santander Cash (O)&nbsp; &nbsp; &nbsp; &nbsp;&nbsp;
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        Consumer’s birthdate, format: DD.MM.YYYY
      </td>
    </tr>
    
    <tr>
      <td>
        <pre>
iban</pre>
      </td>
      
      <td>
        SEPA Direct Debit (M)
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        Consumer’s IBAN - International Bank Account Number
      </td>
    </tr>
    
    <tr>
      <td>
        <pre>
mandateDate</pre>
      </td>
      
      <td>
        SEPA Direct Debit (M)
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        <p>
          This field allows you to provide the date of the mandate and to reference to the date of the original mandate when performing recurring Direct Debit transactions.&nbsp;<br /> The date needs to be submitted in format YYYYMMDD.
        </p>
      </td>
    </tr>
    
    <tr>
      <td>
        <pre>
mandateReference  </pre>
      </td>
      
      <td>
        SEPA Direct Debit (M)
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        <p>
          This field allows you to transmit a Mandate Reference for Direct Debit payments.
        </p>
        
        <p>
          Please note the regulatory requisite to keep the Mandate Reference unambiguous.
        </p>
      </td>
    </tr>
    
    <tr>
      <td>
        <pre>
mandateType</pre>
      </td>
      
      <td>
        SEPA Direct Debit (M)
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        This field allows you to process Direct Debit transactions that are based on mandates for recurring collections. The mandate type can be set to ‘single’ for single (one-off) debit collections, to ‘firstCollection’ when submitting the initial transaction related to a mandate for recurring Direct Debit collections, to ‘recurringCollection’ for subsequent recurring transactions or to ‘finalCollection’ for the last direct debit in a series of recurring direct debits.
      </td>
    </tr>
    
    <tr>
      <td>
        <pre>
mandateUrl</pre>
      </td>
      
      <td>
        SEPA Direct Debit (M)
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        When your store is enabled for SEPA Direct Debit as part of the Local Payments offering, this field allows you to transmit a valid URL of SEPA Direct Debit mandate to enable the Risk and Compliance department to access the details. Please note that it is mandatory to submit a mandateReference and a mandateDate together with a mandateUrl in case you manage SEPA Direct Debit mandates on your side in the combination with the Local Payments offering.
      </td>
    </tr>
    
    <tr>
      <td>
        <pre>
mobileMode</pre>
      </td>
      
      <td>
        <span lang="DE"><span><span>Alipay (O)</span></span></span>
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        <span lang="DE"><span><span>You can submit this parameter with the value ‘true’ to enable Alipay for mobile web.&nbsp;</span></span></span><span lang="EN-US"><span>i.e.: the mobile enabled variant of Alipay.</span></span>
      </td>
    </tr>
    
    <tr>
      <td>
        <pre>
language</pre>
      </td>
      
      <td>
        WeChat Pay (O)
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        <span lang="EN-US"><span>Locale identifier for the payment page</span></span>
      </td>
    </tr>
  </tbody>
</table>

### &nbsp;

### Initiating a Return transaction&nbsp;

In cases where Return transactions are supported for the selected payment method, you can initiate a Return transaction with a reference to the Transaction ID of the original Sale transaction.

> [Return][2]

&nbsp;

### Options for SEPA Direct Debit

When you manage SEPA Direct Debit mandates on your side you can use these in combination with the Local Payments offering by submitting the reference and date of the mandate as well as a link to the mandate itself. This option is&nbsp;especially useful in cases where you have a large number of mandates on file from previously used solutions and want to continue to use these mandates.

<table>
  <tbody>
    <tr>
      <td>
        <strong>Field Name</strong>
      </td>
      
      <td>
        <strong><span lang="EN-US"><span>Description</span></span></strong>
      </td>
    </tr>
    
    <tr>
      <td>
        <pre>
email</pre>
      </td>
      
      <td>
        Consumer’s email address
      </td>
    </tr>
    
    <tr>
      <td>
        <pre>
iban</pre>
      </td>
      
      <td>
        Consumer’s IBAN - International Bank Account Number
      </td>
    </tr>
    
    <tr>
      <td>
        <pre>
mandateType</pre>
      </td>
      
      <td>
        <p>
          Sequence type of Direct Debit, defaults to ‘single’&nbsp;<br /> Values:<br /> single - Direct Debit is executed once<br /> firstCollection&nbsp; - First Direct Debit in a series of recurring<br /> recurringCollection – Follow-up Direct Debit in a series of recurring<br /> finalCollection – Last Direct Debit in a series of recurring
        </p>
      </td>
    </tr>
    
    <tr>
      <td>
        <pre>
mandateReference</pre>
      </td>
      
      <td>
        To be populated with the mandate reference
      </td>
    </tr>
    
    <tr>
      <td>
        <pre>
mandateDate</pre>
      </td>
      
      <td>
        To be populated with the initial mandate signature date
      </td>
    </tr>
    
    <tr>
      <td>
        <pre>
mandateUrl</pre>
      </td>
      
      <td>
        To be populated with the valid URL of the SEPA mandate to enable the Risk and Compliance department to access the Details
      </td>
    </tr>
  </tbody>
</table>

&nbsp;

When you do not want to manage the SEPA Direct Debit mandates on your side, you can use a solution where Fiserv handles the mandates for you. Upon receiving the valid transaction request, the gateway displays a hosted page to your customer with the mandate text and&nbsp;assigned mandate reference. As part of the gateway’s response, you receive the mandate reference and mandate date, which have to be used in case of the subsequent payments under this mandate.

##### Single Payment or First Payment in Recurring Series

<table>
  <tbody>
    <tr>
      <td>
        <strong>Field Name</strong>
      </td>
      
      <td>
        <strong><span lang="EN-US"><span>Description</span></span></strong>
      </td>
    </tr>
    
    <tr>
      <td>
        <pre>
email</pre>
      </td>
      
      <td>
        Consumer’s email address
      </td>
    </tr>
    
    <tr>
      <td>
        <pre>
iban</pre>
      </td>
      
      <td>
        Consumer’s IBAN - International Bank Account Number
      </td>
    </tr>
    
    <tr>
      <td>
        <pre>
mandateType   </pre>
      </td>
      
      <td>
        <p>
          Sequence type of Direct Debit, defaults to ‘single’<br /> Values:<br /> single - Direct Debit is executed once<br /> firstCollection&nbsp; - First Direct Debit in a series of recurring
        </p>
      </td>
    </tr>
  </tbody>
</table>

##### &nbsp;

##### Follow-up Payments in Recurring Series

<table>
  <tbody>
    <tr>
      <td>
        <strong>Field Name</strong>
      </td>
      
      <td>
        <strong><span lang="EN-US"><span>Description</span></span></strong>
      </td>
    </tr>
    
    <tr>
      <td>
        <pre>
email</pre>
      </td>
      
      <td>
        Consumer’s email address
      </td>
    </tr>
    
    <tr>
      <td>
        <pre>
iban</pre>
      </td>
      
      <td>
        Consumer’s IBAN - International Bank Account Number
      </td>
    </tr>
    
    <tr>
      <td>
        <pre>
mandateType</pre>
      </td>
      
      <td>
        <p>
          Sequence type of Direct Debit, defaults to ‘single’<br /> Values:<br /> recurringCollection – Follow-up Direct Debit in a series of recurring<br /> finalCollection – Last Direct Debit in a series of recurring
        </p>
      </td>
    </tr>
    
    <tr>
      <td>
        <pre>
mandateReference </pre>
      </td>
      
      <td>
        To be populated with the mandate reference from the response
      </td>
    </tr>
    
    <tr>
      <td>
        <pre>
mandateDate</pre>
      </td>
      
      <td>
        To be populated with the initial mandate signature date from the response
      </td>
    </tr>
  </tbody>
</table>

 [1]: http://docs.firstdata.com/org/gateway/node/90
 [2]: http://docs.firstdata.com/org/gateway/node/223
