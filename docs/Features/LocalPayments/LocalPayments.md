---
title: Local Payments
author: anna.kopylowicz@firstdata.de
---

_The following information is only relevant if you are using the First Data Local Payments solution._

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
        <strong>Comment</strong>
      </td>
      
      <td>
        &nbsp;
      </td>
    </tr>
    
    <tr>
      <td>
        paymentMethod
      </td>
      
      <td>
        &nbsp;&nbsp;
      </td>
      
      <td>
        You can submit the parameter <em>paymentMethod</em> in your transaction request to determine the payment method to be used for the transaction. See possible values <a href="http://test-ndpfdc.pantheonsite.io/org/gateway/node/55">here</a>.<br /> If you do not submit this parameter, the Gateway will display a page to your consumer to choose from the payment methods that are supported for the combination of the consumer’s country and the transaction currency.
      </td>
      
      <td>
        &nbsp;
      </td>
    </tr>
    
    <tr>
      <td>
        bname
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
        bcountry
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

### &nbsp;

### Payment Method Specific Fields to be Considered for Local Payments

(M)=Mandatory&nbsp;(O)=Optional

<table>
  <tbody>
    <tr>
      <td>
        <strong>Field </strong>
      </td>
      
      <td>
        <strong>Relevant for </strong>
      </td>
      
      <td>
        &nbsp;&nbsp;
      </td>
      
      <td>
        <strong>Comment</strong>
      </td>
    </tr>
    
    <tr>
      <td>
        nationalId
      </td>
      
      <td>
        Boleto Bancário (M)<br /> Santander (M)<br /> Santander Cash (M)
      </td>
      
      <td>
        &nbsp;&nbsp;
      </td>
      
      <td>
        Consumer’s National ID (up to 30 characters)
      </td>
    </tr>
    
    <tr>
      <td>
        customerid
      </td>
      
      <td>
        AstroPay Card (M)<br /> AstroPay Direct (M)<br /> Boleto Bancário (M)<br /> Entercash (M)<br /> Santander (M)<br /> Santander Cash (M)
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        Unique reference to identify the consumer
      </td>
    </tr>
    
    <tr>
      <td>
        email
      </td>
      
      <td>
        Boleto Bancário (M)<br /> SEPA Direct Debit (M)<br /> Santander (M)<br /> Santander Cash (M)
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
        bbirthday
      </td>
      
      <td>
        Boleto Bancário (O)<br /> Santander (O)<br /> Santander Cash (O)
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
        bic&nbsp;
      </td>
      
      <td>
        Entercash (O)<br /> giropay (O)<br /> SOFORT Banking (O)
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        Consumer’s BIC – Business Identifier Code (8 or 11 Digits)
      </td>
    </tr>
    
    <tr>
      <td>
        iban
      </td>
      
      <td>
        Entercash (O)<br /> SEPA Direct Debit (M)
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        Consumer’s IBAN - International Bank Account Number (22 Digits)
      </td>
    </tr>
    
    <tr>
      <td>
        mandateDate
      </td>
      
      <td>
        SEPA Direct Debit (M)
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        This field allows you to provide the date of the mandate and to reference to the date of the original mandate when performing recurring Direct Debit transactions. The date needs to be submitted in format YYYYMMDD.
      </td>
    </tr>
    
    <tr>
      <td>
        mandateReference
      </td>
      
      <td>
        SEPA Direct Debit (M)
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        This field allows you to transmit a Mandate Reference for Direct Debit payments. Please note the regulatory requisite to keep the Mandate Reference unambiguous.
      </td>
    </tr>
    
    <tr>
      <td>
        mandateType
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
        mandateUrl
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
        phone
      </td>
      
      <td>
        QIWI (M)
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        Consumer’s phone number
      </td>
    </tr>
  </tbody>
</table>

&nbsp;

### Initiating a Return transaction&nbsp;

In cases where Return transactions are supported for the selected payment method, you can initiate a Return transaction with a reference to the Transaction ID of the original Sale transaction.

> Return

&nbsp;

### Options for SEPA Direct Debit

When you manage SEPA Direct Debit mandates on your side you can use these in combination with the Local Payments offering by submitting the reference and date of the mandate as well as a link to the mandate itself. This is especially useful in cases where you have a large number of mandates on file from previously used solutions and want to continue to use these mandates.

<table>
  <tbody>
    <tr>
      <td>
        <strong>Field</strong>
      </td>
      
      <td>
        <strong>Description</strong>
      </td>
    </tr>
    
    <tr>
      <td>
        email
      </td>
      
      <td>
        Consumer’s email address
      </td>
    </tr>
    
    <tr>
      <td>
        iban
      </td>
      
      <td>
        Consumer’s IBAN - International Bank Account Number (22 Digits)
      </td>
    </tr>
    
    <tr>
      <td>
        mandateType
      </td>
      
      <td>
        <p>
          Sequence type of Direct Debit, defaults to ‘single’<br /> Values:<br /> single - Direct Debit is executed once<br /> firstCollection&nbsp; - First Direct Debit in a series of recurring<br /> recurringCollection – Follow-up Direct Debit in a series of recurring<br /> finalCollection – Last Direct Debit in a series of recurring
        </p>
      </td>
    </tr>
    
    <tr>
      <td>
        mandateReference
      </td>
      
      <td>
        To be populated with the mandate reference
      </td>
    </tr>
    
    <tr>
      <td>
        mandateDate
      </td>
      
      <td>
        To be populated with the initial mandate signature date
      </td>
    </tr>
    
    <tr>
      <td>
        mandateUrl
      </td>
      
      <td>
        To be populated with the valid URL of the SEPA mandate to enable the Risk and Compliance department to access the Details
      </td>
    </tr>
  </tbody>
</table>

&nbsp;

When you do not want to manage the SEPA Direct Debit mandates on your side, you can instead use the _out-of-box_ solution offered by First Data.

##### Single Payment or First Payment in Recurring Series

<table>
  <tbody>
    <tr>
      <td>
        <strong>Field</strong>
      </td>
      
      <td>
        <strong>Description</strong>
      </td>
    </tr>
    
    <tr>
      <td>
        email
      </td>
      
      <td>
        Consumer’s email address
      </td>
    </tr>
    
    <tr>
      <td>
        iban
      </td>
      
      <td>
        Consumer’s IBAN - International Bank Account Number (22 Digits)
      </td>
    </tr>
    
    <tr>
      <td>
        mandateType
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
        <strong>Description</strong>
      </td>
    </tr>
    
    <tr>
      <td>
        email
      </td>
      
      <td>
        Consumer’s email address
      </td>
    </tr>
    
    <tr>
      <td>
        iban
      </td>
      
      <td>
        Consumer’s IBAN - International Bank Account Number (22 Digits)
      </td>
    </tr>
    
    <tr>
      <td>
        mandateType
      </td>
      
      <td>
        <p>
          Sequence type of Direct Debit, defaults to ‘single’<br /> Values:<br /> recurringCollection – Follow-up Direct Debit in a series of recurring<br /> finalCollection – Last Direct Debit in a series of recurring
        </p>
      </td>
    </tr>
    
    <tr>
      <td>
        mandateReference
      </td>
      
      <td>
        To be populated with the mandate reference from the response
      </td>
    </tr>
    
    <tr>
      <td>
        mandateDate
      </td>
      
      <td>
        To be populated with the initial mandate signature date from the response
      </td>
    </tr>
  </tbody>
</table>

 [1]: http://test-ndpfdc.pantheonsite.io/org/gateway/node/90
