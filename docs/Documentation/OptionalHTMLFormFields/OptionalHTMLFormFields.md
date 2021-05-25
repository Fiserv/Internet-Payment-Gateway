---
title: Optional HTML Form Fields
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
            ‘combinedpage’ is the standard when using a hosted payment page
          </li>
          <li>
            ‘classic’ for special cases that require a fall-back, e.g. where consumers use old operating systems with out-dated browser versions
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
        <table>
          <tbody>
            <tr>
              <td>
                &nbsp;
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
                    
                    <tr>
                      <td>
                        <span lang="EN-US"><span>Handelsbanken</span></span>
                      </td>
                      
                      <td>
                        <span lang="EN-US"><span>HANDNL2A</span></span>
                      </td>
                    </tr>
                    
                    <tr>
                      <td>
                        <span lang="EN-US"><span>Moneyou</span></span>
                      </td>
                      
                      <td>
                        <span lang="EN-US"><span>MOYONL21</span></span>
                      </td>
                    </tr>
                    
                    <tr>
                      <td>
                        <span lang="EN-IN"><span><span>Revolut</span></span></span>
                      </td>
                      
                      <td>
                        <span lang="EN-IN"><span><span><span><span>REVOLT21</span></span></span></span></span>
                      </td>
                    </tr>
                  </tbody>
                </table>
              </td>
            </tr>
          </tbody>
        </table>
        
        <p>
          &nbsp;
        </p>
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
          <tbody>
            <tr>
              <td>
                <p>
                  <strong><span lang="EN-US">Language</span></strong>
                </p>
              </td>
              
              <td>
                <p>
                  <strong><span lang="EN-US">Value</span></strong>
                </p>
              </td>
            </tr>
            
            <tr>
              <td>
                <p>
                  <span lang="EN-US">Chinese (simplified)</span>
                </p>
              </td>
              
              <td>
                <p>
                  <span lang="EN-US">zh_CN</span>
                </p>
              </td>
            </tr>
            
            <tr>
              <td>
                <p>
                  <span lang="EN-US">Chinese (traditional)</span>
                </p>
              </td>
              
              <td>
                <p>
                  <span lang="EN-US">zh_TW</span>
                </p>
              </td>
            </tr>
            
            <tr>
              <td>
                <p>
                  <span lang="EN-US">Czech</span>
                </p>
              </td>
              
              <td>
                <p>
                  <span lang="EN-US">cs_CZ</span>
                </p>
              </td>
            </tr>
            
            <tr>
              <td>
                <p>
                  <span lang="EN-US">Danish</span>
                </p>
              </td>
              
              <td>
                <p>
                  <span lang="EN-US">da_DK</span>
                </p>
              </td>
            </tr>
            
            <tr>
              <td>
                <p>
                  <span lang="EN-US">Dutch</span>
                </p>
              </td>
              
              <td>
                <p>
                  <span lang="EN-US">nl_NL</span>
                </p>
              </td>
            </tr>
            
            <tr>
              <td>
                <p>
                  <span lang="EN-US">English (USA)</span>
                </p>
              </td>
              
              <td>
                <p>
                  <span lang="EN-US">en_US</span>
                </p>
              </td>
            </tr>
            
            <tr>
              <td>
                <p>
                  <span lang="EN-US">English (UK)</span>
                </p>
              </td>
              
              <td>
                <p>
                  <span lang="EN-US">en_GB</span>
                </p>
              </td>
            </tr>
            
            <tr>
              <td>
                <p>
                  <span lang="EN-US">Finnish</span>
                </p>
              </td>
              
              <td>
                <p>
                  <span lang="EN-US">fi_FI</span>
                </p>
              </td>
            </tr>
            
            <tr>
              <td>
                <p>
                  <span lang="EN-US">French</span>
                </p>
              </td>
              
              <td>
                <p>
                  <span lang="EN-US">fr_FR</span>
                </p>
              </td>
            </tr>
            
            <tr>
              <td>
                <p>
                  <span lang="EN-US">German</span>
                </p>
              </td>
              
              <td>
                <p>
                  <span lang="EN-US">de_DE</span>
                </p>
              </td>
            </tr>
            
            <tr>
              <td>
                <p>
                  <span lang="EN-US">Greek</span>
                </p>
              </td>
              
              <td>
                <p>
                  <span lang="EN-US">el_GR</span>
                </p>
              </td>
            </tr>
            
            <tr>
              <td>
                <p>
                  <span lang="EN-US">Hungarian</span>
                </p>
              </td>
              
              <td>
                <p>
                  <span lang="EN-US">hu_HU</span>
                </p>
              </td>
            </tr>
            
            <tr>
              <td>
                <p>
                  <span lang="EN-US">Italian</span>
                </p>
              </td>
              
              <td>
                <p>
                  <span lang="EN-US">it_IT</span>
                </p>
              </td>
            </tr>
            
            <tr>
              <td>
                <p>
                  <span lang="EN-US"><span>Japanese</span></span>
                </p>
              </td>
              
              <td>
                <p>
                  <span lang="EN-US"><span>ja_JP</span></span>
                </p>
              </td>
            </tr>
            
            <tr>
              <td>
                <p>
                  <span lang="EN-US">Norwegian&nbsp;<span>(Bokmål)&nbsp;</span></span>
                </p>
              </td>
              
              <td>
                <p>
                  <span lang="EN-US">nb_NO</span>
                </p>
              </td>
            </tr>
            
            <tr>
              <td>
                <p>
                  <span lang="EN-US">Polish</span>
                </p>
              </td>
              
              <td>
                <p>
                  <span lang="EN-US">pl_PL</span>
                </p>
              </td>
            </tr>
            
            <tr>
              <td>
                <p>
                  <span lang="EN-US">Portuguese (Brazil)</span>
                </p>
              </td>
              
              <td>
                <p>
                  <span lang="EN-US">pt_BR</span>
                </p>
              </td>
            </tr>
            
            <tr>
              <td>
                <p>
                  <span lang="EN-US">Serbian&nbsp;<span>(Serbia)</span></span>
                </p>
              </td>
              
              <td>
                <p>
                  <span lang="EN-US">sr_RS</span>
                </p>
              </td>
            </tr>
            
            <tr>
              <td>
                <p>
                  <span lang="EN-US">Slovak</span>
                </p>
              </td>
              
              <td>
                <p>
                  <span lang="EN-US">sk_SK</span>
                </p>
              </td>
            </tr>
            
            <tr>
              <td>
                <p>
                  Slovenian&nbsp;
                </p>
              </td>
              
              <td>
                <p>
                  <span lang="EN-US"><span><span class="msoIns"><span>sl_SI</span></span></span></span>
                </p>
              </td>
            </tr>
            
            <tr>
              <td>
                <p>
                  <span lang="EN-US">Spanish (Spain)</span>
                </p>
              </td>
              
              <td>
                <p>
                  <span lang="EN-US">es_ES</span>
                </p>
              </td>
            </tr>
            
            <tr>
              <td>
                <p>
                  Spanish (Mexico)
                </p>
              </td>
              
              <td>
                <p>
                  <span lang="EN-US"><span>es_MX</span></span>
                </p>
              </td>
            </tr>
            
            <tr>
              <td>
                <p>
                  <span lang="EN-US">Swedish</span>
                </p>
              </td>
              
              <td>
                <p>
                  <span lang="EN-US">sv_SE</span>
                </p>
              </td>
            </tr>
          </tbody>
        </table>
        
        <p>
          &nbsp;
        </p>
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
          Allows you to assign a unique ID for the transaction with up to 40 characters. This ID can be used to reference to this transactions in a PostAuth or Void request<br /> (referencedMerchantTransactionId).
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
        This field allows you to assign a unique ID for your order with up to 100 characters. If you choose not to assign an order ID, the Fiserv system will automatically generate one for you.<br /> Please note that for Direct Debit transactions, a maximum of 78 characters can be submitted to the bank.
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
          This field allows you to submit an identifier for your customer with up to 32 characters.<br /> <br /> Please note that for:
        </p>
        
        <ul>
          <li>
            Direct Debit transactions, the Customer ID can be submitted to the bank, depending on the length of the Order ID. The maximum amount of characters that can be submitted to the bank for the combination of Customer ID and Order ID is 78.
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
  </tbody>
</table>

##### &nbsp;

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
          <span><span><span lang="EN-US">Line items are regular&nbsp;key-value parameters (URL-encoded), where:</span></span></span>
        </p>
        
        <ul>
          <li>
            <span><span><span lang="EN-US">the name is a combination of the keyword item and a number, where the number indicates the list position e.g.: item1</span></span></span>
          </li>
          <li>
            <span><span><span lang="EN-US">the value is represented by a semicolon-separated list of values, where the position indicates the meaning of the list item property e.g.: <1>;<2>;<3>;<4>;<5>;<6>;<7></span></span></span>
          </li>
        </ul>
        
        <p>
          The ‘item1’ to ‘item999’ parameters allow you to send basket information in the following format:
        </p>
        
        <p class="text-align-center">
          <em>id;description;quantity;item_total_price;sub_total;vat_tax;shipping</em>
        </p>
        
        <p>
          'shipping' always has to be set to '0' for single line items. If you want to include a shipping fee for an order, please use the predefined id IPG_SHIPPING.
        </p>
        
        <p>
          For other fees that you may want to add to the total order, you can use the predefined id IPG_HANDLING.<br /> When you want to apply a discount, you should include an item with a negative amount and change accordingly the total amount of the order. Do not forget to regard the ‘quantity’ when calculating the values e.g.: subtotal and VAT since they are fixed by items.
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
        <p>
          <span><span><span lang="EN-US">This parameter allows you to use the secure and hosted payment form capabilities within your own application. Possible values are:</span></span></span>
        </p>
        
        <ul>
          <li>
            <span><span><span lang="EN-US">‘MAIL’</span> <span lang="EN-US">(for transactions where the payment details are captured manually and provided in written form the Card Code entry is not allowed) </span></span></span>
          </li>
          <li>
            <span><span><span lang="EN-US">‘PHONE’ (for transactions where you have received the order over the phone and enter the payment details yourself the Card Code entry is required)</span></span></span>
          </li>
          <li>
            <span lang="EN-US"><span>‘ECI‘ (for standard usage in an eCommerce environment)</span></span>
          </li>
        </ul>
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

#### &nbsp;

#### HTML Form Fields for Specific Functionalities

Some&nbsp;functionalities create the need additional fields or fields that become mandatory which would otherwise be optional, either for the addendum to be achieved, scheme requirements met for specific MCCs or to send required information for a specific payment method, as below:

  * Purchasing Cards Level II and Level III

  * MCC6012 Mandate in the UK

  * DCC and Installment Card Related

  * SEPA Direct Debit

  * MasterPass

  * China Domestic Payments

[Click here to view the HTML fields relevant to these.][1]

 [1]: https://docs.firstdata.com/org/gateway/node/455
