---
title: Optional HTML Form Fields
author: steffen.dangel@firstdata.de
---

If you post a HTML form to initiate the payment, there are a number of optional fields that you can include in your request for different purpose.

### Checkout Experience Related Fields

<table>
  <thead>
    <tr>
      <th>
        Field
      </th>
      
      <th>
        &nbsp;&nbsp;
      </th>
      
      <th>
        Comment
      </th>
    </tr>
  </thead>
  
  <tbody>
    <tr>
      <td>
        checkoutoption
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        <p>
          This field allows you to set the checkout option to
        </p>
        
        <ul>
          <li>
            'simpleform' in case you want to work with an <a href="http://test-ndpfdc.pantheonsite.io/org/gateway/node/210">iFrame integration</a>
          </li>
          <li>
            ‘combinedpage’ in case you want to use a hosted payment page
          </li>
          <li>
            ‘classic’ for transactions with payment methods that are not supported with the other two options
          </li>
        </ul>
      </td>
    </tr>
    
    <tr>
      <td>
        idealIssuerID
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        <p>
          This parameter can be used to submit the iDEAL issuing bank in case you let your customers select the issuer within your shop environment. If you do not pass this value for an iDEAL transaction, a hosted selection form will be displayed to your customer.
        </p>
        
        <table>
          <thead>
            <tr>
              <th>
                iDEAL Issuer
              </th>
              
              <th>
                Value
              </th>
            </tr>
          </thead>
          
          <tbody>
            <tr>
              <td>
                ABN AMRO
              </td>
              
              <td>
                ABNANL2A
              </td>
            </tr>
            
            <tr>
              <td>
                ING
              </td>
              
              <td>
                INGBNL2A
              </td>
            </tr>
            
            <tr>
              <td>
                SNS Bank
              </td>
              
              <td>
                SNSBNL2A
              </td>
            </tr>
            
            <tr>
              <td>
                van Lanschot
              </td>
              
              <td>
                FVLBNL22
              </td>
            </tr>
            
            <tr>
              <td>
                Triodos Bank
              </td>
              
              <td>
                TRIONL2U
              </td>
            </tr>
            
            <tr>
              <td>
                Knab
              </td>
              
              <td>
                KNABNL2H
              </td>
            </tr>
            
            <tr>
              <td>
                Rabobank
              </td>
              
              <td>
                RABONL2U
              </td>
            </tr>
            
            <tr>
              <td>
                RegioBank
              </td>
              
              <td>
                RBRBNL21
              </td>
            </tr>
            
            <tr>
              <td>
                ASN Bank
              </td>
              
              <td>
                ASNBNL21
              </td>
            </tr>
            
            <tr>
              <td>
                Bunq
              </td>
              
              <td>
                BUNQNL2A
              </td>
            </tr>
          </tbody>
        </table>
      </td>
    </tr>
    
    <tr>
      <td>
        language
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        <p>
          This parameter can be used to override the default payment page language configured for your merchant store.<br /> The following values are currently possible:
        </p>
        
        <table>
          <thead>
            <tr>
              <th>
                Language
              </th>
              
              <th>
                Value
              </th>
            </tr>
          </thead>
          
          <tbody>
            <tr>
              <td>
                Chinese (simplified)
              </td>
              
              <td>
                zh_CN
              </td>
            </tr>
            
            <tr>
              <td>
                Chinese (traditional)
              </td>
              
              <td>
                zh_TW
              </td>
            </tr>
            
            <tr>
              <td>
                Czech
              </td>
              
              <td>
                cs_CZ
              </td>
            </tr>
            
            <tr>
              <td>
                Dutch
              </td>
              
              <td>
                nl_NL
              </td>
            </tr>
            
            <tr>
              <td>
                English (USA)
              </td>
              
              <td>
                en_US
              </td>
            </tr>
            
            <tr>
              <td>
                English (UK)
              </td>
              
              <td>
                en_GB
              </td>
            </tr>
            
            <tr>
              <td>
                Finnish
              </td>
              
              <td>
                fi_FI
              </td>
            </tr>
            
            <tr>
              <td>
                French
              </td>
              
              <td>
                fr_FR
              </td>
            </tr>
            
            <tr>
              <td>
                German
              </td>
              
              <td>
                de_DE
              </td>
            </tr>
            
            <tr>
              <td>
                Greek
              </td>
              
              <td>
                el_GR
              </td>
            </tr>
            
            <tr>
              <td>
                Italian
              </td>
              
              <td>
                it_IT
              </td>
            </tr>
            
            <tr>
              <td>
                Polish
              </td>
              
              <td>
                pl_PL
              </td>
            </tr>
            
            <tr>
              <td>
                Portuguese (Brazil)
              </td>
              
              <td>
                pt_BR
              </td>
            </tr>
            
            <tr>
              <td>
                Serbian
              </td>
              
              <td>
                sr_RS
              </td>
            </tr>
            
            <tr>
              <td>
                Slovak
              </td>
              
              <td>
                sk_SK
              </td>
            </tr>
            
            <tr>
              <td>
                Spanish
              </td>
              
              <td>
                es_ES
              </td>
            </tr>
          </tbody>
        </table>
      </td>
    </tr>
    
    <tr>
      <td>
        mobileMode
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        Only in relation to checkoutoption 'classic': if your customer uses a mobile device for shopping at your online store you can submit this parameter with the value ‘true’. This will lead your customer to a payment page flow that has been specifically designed for mobile devices.
      </td>
    </tr>
    
    <tr>
      <td>
        paymentMethod
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        <p>
          If you let the customer select the payment method (e. g. MasterCard, Visa, Direct Debit) in your shop environment or want to define the payment type yourself, transmit the parameter ‘paymentMethod’ along with your Sale or PreAuth transaction.<br /> If you do not submit this parameter, the payment gateway will display a drop-down menu to the customer to choose from the payment methods available for your shop.
        </p>
        
        <p>
          > <a href="http://test-ndpfdc.pantheonsite.io/org/gateway/node/55">See valid values here</a>
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
  </tbody>
</table>

### &nbsp;

### Transaction Identifiers

<table>
  <thead>
    <tr>
      <th>
        Field
      </th>
      
      <th>
        &nbsp;&nbsp;
      </th>
      
      <th>
        Comment
      </th>
    </tr>
    
    <tr>
      <td>
        merchantTransactionId
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        <p>
          Allows you to assign a unique ID for the transaction. This ID can be used to reference to this transactions in a PostAuth or Void request<br /> (referencedMerchantTransactionId).
        </p>
      </td>
    </tr>
    
    <tr>
      <td>
        oid
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        This field allows you to assign a unique ID for your order. If you choose not to assign an order ID, the First Data system will automatically generate one for you.<br /> Please note that for Direct Debit transactions, a maximum of 78 characters can be submitted to the bank.
      </td>
    </tr>
    
    <tr>
      <td>
        referencedMerchantTransactionID
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        This field allows to reference to a merchantTransactionId of a<br /> transaction when performing a Void. This can be used as an alternative to ipgTransactionId if you assigned a merchantTransactionId in the original transaction request.
      </td>
    </tr>
  </thead>
</table>

&nbsp;

### Consumer Information

<table>
  <thead>
    <tr>
      <th>
        Field
      </th>
      
      <th>
        &nbsp;&nbsp;
      </th>
      
      <th>
        Comment
      </th>
    </tr>
  </thead>
  
  <tbody>
    <tr>
      <td>
        customerid
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        <p>
          This field allows you to transmit any value, e. g. your ID for the customer.<br /> Please note that for:
        </p>
        
        <ul>
          <li>
            Direct Debit transactions, the Customer ID can be submitted to the bank, depending on the length of the Order ID. The maximum amount of characters that can be submitted to the bank is 78.
          </li>
          <li>
            iDEAL transactions, the Customer ID can be submitted in your request filled in with any relevant data which can be populated in a field in the iDEAL TransactionRequest to be displayed on your consumers’ bank account statements.
          </li>
        </ul>
      </td>
    </tr>
    
    <tr>
      <td>
        ponumber
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        This field allows you to submit a Purchase Order Number with up to 50 characters.
      </td>
    </tr>
  </tbody>
</table>

### &nbsp;

### Card Related Fields

<table>
  <thead>
    <tr>
      <th>
        Field
      </th>
      
      <th>
        &nbsp;&nbsp;
      </th>
      
      <th>
        Comment
      </th>
    </tr>
  </thead>
  
  <tbody>
    <tr>
      <td>
        cardFunction
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        <p>
          This field allows you to indicate the card function in case of combo cards which provide credit and debit functionality on the same card. It can be set to ‘credit’ or ‘debit’.<br /> The field can also be used to validate the card type in a way that transactions where the submitted card function does not match the card’s capabilities will be declined. If you e.g. submit “cardFunction=debit” and the card is a credit card, the transaction will be declined.
        </p>
      </td>
    </tr>
    
    <tr>
      <td>
        dccInquiryId
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        Inquiry ID for a Dynamic Pricing request. Used to send the Inquiry ID you have obtained via an API call. This value will be used to retrieve the currency conversion information (exchange rate, converted amount) for this transaction.
      </td>
    </tr>
    
    <tr>
      <td>
        numberOfInstallments
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        This parameter allows you to set the number of instalments for a Sale transaction if your customer pays the amount in several parts.
      </td>
    </tr>
    
    <tr>
      <td>
        installmentsInterest
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        This parameter allows you to choose, if instalment interest should be applied or not, the values “true” or “false” are currently possible.
      </td>
    </tr>
    
    <tr>
      <td>
        installmentDelayMonths
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        This parameter allows you to delay the first instalment payment for several months, values 2-99 are currently possible.
      </td>
    </tr>
  </tbody>
</table>

### &nbsp;

### Information Required For Specific Payment Methods

##### SEPA Direct Debit

<table>
  <thead>
    <tr>
      <th>
        Field
      </th>
      
      <th>
        &nbsp;&nbsp;
      </th>
      
      <th>
        Comment
      </th>
    </tr>
    
    <tr>
      <td>
        mandateDate
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        <p>
          This field allows you to reference to the date of the original mandate when performing recurring Direct Debit transactions. The date needs to be submitted in format YYYYMMDD. Please note that this is a mandatory field for recurring Direct Debit transactions.
        </p>
      </td>
    </tr>
    
    <tr>
      <td>
        mandateReference
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
        &nbsp;
      </td>
      
      <td>
        This field allows you to process Direct Debit transactions that are based on mandates for recurring collections. The mandate type can be set to ‘single’ for single (one-off) debit collections, to ‘firstCollection’ when submitting the initial transaction related to a mandate for recurring Direct Debit collections, to ‘recurringCollection’ for subsequent recurring transactions or to ‘finalCollection’ for the last direct debit in a series of recurring direct debits. Transactions where this parameter is not submitted by the merchant will be flagged as a single debit collection.<br /> Please note that it is mandatory to submit a mandateReference in case of recurring collections.
      </td>
    </tr>
    
    <tr>
      <td>
        mandateUrl
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        When your store is enabled for SEPA Direct Debit as part of the Local Payments offering, this field allows you to transmit a valid URL of SEPA Direct Debit mandate to enable the Risk and Compliance department to access the details.<br /> Please note that it is mandatory to submit a mandateReference and a mandateDate together with a mandateUrl in case you manage SEPA Direct Debit mandates on your side in the combination with the Local Payments offering.
      </td>
    </tr>
  </thead>
</table>

##### &nbsp;

##### MasterPass

<table>
  <thead>
    <tr>
      <th>
        Field
      </th>
      
      <th>
        &nbsp;&nbsp;
      </th>
      
      <th>
        Comment
      </th>
    </tr>
    
    <tr>
      <td>
        reviewOrder
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        <p>
          MasterPass-specific parameter for scenarios where the final amount needs to be confirmed by the customer after returning from the Wallet. Set the value for this parameter to ‘true’ in order to indicate that the final transaction amount needs to be reviewed by the cardholder.
        </p>
      </td>
    </tr>
    
    <tr>
      <td>
        reviewURL
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        MasterPass-specific parameter for scenarios where the final amount needs to be confirmed by the customer after returning from the MasterPass environment. Use this parameter to indicate where the customer shall be redirected to in order to review and complete the transaction after having clicked on “Finish shopping” within the Wallet.
      </td>
    </tr>
  </thead>
</table>

### &nbsp;

### Additional Transaction Information

<table>
  <thead>
    <tr>
      <th>
        Field
      </th>
      
      <th>
        &nbsp;&nbsp;
      </th>
      
      <th>
        Comment
      </th>
    </tr>
  </thead>
  
  <tbody>
    <tr>
      <td>
        comments
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        <p>
          Place any comments here about the transaction.
        </p>
      </td>
    </tr>
    
    <tr>
      <td>
        dynamicMerchantName
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        The name of the merchant to be displayed on the cardholder’s statement. The length of this field should not exceed 25 characters. If you want to use this field, please contact your local support team to verify if this feature is supported in your country.
      </td>
    </tr>
    
    <tr>
      <td>
        invoicenumber
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        This field allows you to transmit any value, e. g. an invoice number or class of goods. Please note that the maximum length for this parameter is 48 characters.
      </td>
    </tr>
    
    <tr>
      <td>
        item1 up to item999
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        <p>
          The ‘item1’ to ‘item999’ parameters allow you to send basket information in the following format:<br /> id;description;quantity;item_total_price;sub_total;vat_tax;shipping<br /> 'shipping' always has to be set to '0' for single line items. If you want to include a shipping fee for an order, please use the predefined id IPG_SHIPPING.<br /> For other fees that you may want to add to the total order, you can use the predefined id IPG_HANDLING.<br /> When you want to apply a discount, you should include an item with a negative amount and change accordingly the total amount of the order. Do not forget to regard the ‘quantity’ when calculating the values e.g.: subtotal and VAT since they are fixed by items.
        </p>
        
        <p>
          Examples:<br /> A;Product A;1;5;3;2;0<br /> B;Product B;5;10;7;3;0<br /> C;Product C;2;12;10;2;0<br /> D;Product D;1;-1.0;-0.9;-0.1;0<br /> IPG_SHIPPING;Shipping costs;1;6;5;1;0<br /> IPG_HANDLING;Transaction fee;1;6.0;6.0;0;0
        </p>
      </td>
    </tr>
    
    <tr>
      <td>
        shipping
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        This parameter can be used to submit the shipping fee, in the same format as ‘chargetotal’. If you submit ‘shipping’, the parameters ‘subtotal’ and ‘vattax’ have to be submitted as well. Note that the ‘chargetotal’ has to be equal to ‘subtotal’ plus ‘shipping’ plus ‘vattax’.
      </td>
    </tr>
    
    <tr>
      <td>
        trxOrigin
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        This parameter allows you to use the secure and hosted payment form capabilities within your own application for Mail/Telephone Order (MOTO) payments. Possible values are ‘MOTO‘ (for transactions where you have received the order over the phone or by mail and enter the payment details yourself) and ‘ECI‘ (for standard usage in an eCommerce environment where your customer enters the payment details).
      </td>
    </tr>
    
    <tr>
      <td>
        vattax
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        This field allows you to submit an amount for Value Added Tax or other taxes, e.g. GST in Australia. Please ensure the sub total amount plus shipping plus tax equals the charge total.
      </td>
    </tr>
  </tbody>
</table>
