HTML Form Fields for Specific Functionalities
---

Some functionalities create the need additional fields or fields that become mandatory which would otherwise be optional, either for the addendum to be achieved, scheme requirements met for specific MCCs or to send required information for a specific payment method, as below:

  * 3-D Secure

  * <span lang="EN-US"><span>Credential-on-file transactions</span></span>

  * Purchasing Cards Level II and Level III

  * MCC6012 Mandate in the UK

  * DCC and Installment Card Related&nbsp;

  * Sepa Direct Debit

  * MasterPass

  * China Domestic Payments

  * Korea Domestic Payments

&nbsp;

### <span><span><span><span><span><span><span><span><span><span><span><span><span><span><span><span><span><span>3-D Secure</span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span>

<table class="Table">
  <tbody>
    <tr>
      <td>
        <p>
          <span><span><strong><span lang="EN-US">Field&nbsp;</span></strong></span></span>
        </p>
      </td>
      
      <td>
        <p>
          <span><span><strong><span lang="EN-US">Comment</span></strong></span></span>
        </p>
      </td>
    </tr>
    
    <tr>
      <td>
        <pre>
<span><span><span lang="EN-US">authenticateTransaction</span></span></span></pre>
      </td>
      
      <td>
        <p>
          <span><span><span lang="EN-US">Optional parameter to be set either to ‘true’ or ‘false’ to enable or disable 3-D Secure authentication on a Transaction-by-Transaction basis.</span></span></span>
        </p>
        
        <p>
          <span><span><span lang="EN-US">Example for a transaction with 3-D Secure:</span></span></span>
        </p>
        
        <pre>
<span><span><span lang="EN-US"><span>&lt;input type="hidden" name="authenticateTransaction" value="true"/&gt;</span></span></span></span></pre>
        
        <p>
          <span><span><span lang="EN-US">Example for a transaction without 3D Secure:</span></span></span>
        </p>
        
        <pre>
<span><span><span lang="EN-US"><span>&lt;input type="hidden" name="authenticateTransaction" value="false"/&gt;</span></span></span></span>
</pre>
      </td>
    </tr>
    
    <tr>
      <td>
        <pre>
<span><span><span lang="EN-US">threeDSRequestorChallengeIndicator  </span></span></span></pre>
      </td>
      
      <td>
        <p>
          <span><span><span lang="EN-US">Optional parameter for EMV 3-D Secure (2.0) to be set to: 01,02,03,04 in order to indicate the preferred type of authentication:</span></span></span>
        </p>
        
        <ul>
          <li>
            <span><span><span lang="EN-US">01 - no preference (set as default value) </span></span></span>
          </li>
          <li>
            <span><span><span lang="EN-US">02&nbsp;- no challenge requested&nbsp;</span></span></span>
          </li>
          <li>
            <span><span><span lang="EN-US">03&nbsp;- challenge requested (3DS requestor preference)</span></span></span>
          </li>
          <li>
            <span><span><span lang="EN-US">04&nbsp;- challenge requested (mandate)</span></span></span>
          </li>
        </ul>
      </td>
    </tr>
    
    <tr>
      <td>
        <pre>
threeDSTransType</pre>
      </td>
      
      <td>
        <p>
          The parameter for EMV 3-D Secure (2.0), represents the type of purchased item, mandatory for Visa and Brazilian market, otherwise optional. If no specific value present&nbsp;in the transaction request, default value is used.
        </p>
        
        <ul>
          <li>
            01&nbsp;- Goods/ Service Purchase (default value)
          </li>
          <li>
            03&nbsp;- Check Acceptance&nbsp;
          </li>
          <li>
            10&nbsp;- Account Funding&nbsp;
          </li>
          <li>
            11&nbsp;- Quasi-Cash Transaction&nbsp;
          </li>
          <li>
            28&nbsp;- Prepaid Activation and Load
          </li>
        </ul>
      </td>
    </tr>
    
    <tr>
      <td>
        <pre>
scaExemptionIndicator1</pre>
      </td>
      
      <td>
        <p>
          Use this optional parameter to request an exemption from Strong Customer Authentication (SCA) without the need to perform 3-D Secure authentication. Currently available values:
        </p>
        
        <ul>
          <li>
            Low Value Exemption
          </li>
          <li>
            TRA Exemption
          </li>
          <li>
            Trusted Merchant Exemption
          </li>
          <li>
            SCP Exemption
          </li>
        </ul>
        
        <p>
          <em>Note: please be aware, that this parameter is relevant only for&nbsp;the distribution channels impacted by PSD2 requirements</em>
        </p>
      </td>
    </tr>
    
    <tr>
      <td>
        <pre>
skipTRA</pre>
      </td>
      
      <td>
        <p class="MsoNormal">
          <span lang="EN-US">This optional parameter allows you to use 3D Secure even if the transaction has been evaluated as low risk and would be eligible for an exemption. Currently available values:</span>
        </p>
        
        <ul>
          <li class="MsoNormal">
            <span lang="EN-US">true</span>
          </li>
          <li class="MsoListParagraph">
            <span lang="EN-US">false</span>
          </li>
        </ul>
        
        <p class="MsoNormal">
          <span lang="EN-US">When your store has been set up with Transaction Risk Analysis (TRA) service, but you do want to force 3D Secure authentication for a certain transaction, set ‘skipTRA’ to ‘true’.</span>
        </p>
        
        <p class="MsoNormal">
          <em><span lang="EN-US">Note this parameter is relevant only for the European merchants impacted by the PSD2 requirements.</span></em>
        </p>
      </td>
    </tr>
    
    <tr>
      <td>
        <pre>
oid</pre>
      </td>
      
      <td>
        <p>
          Use this optional parameter to assign an identifier for your order; in case you plan to authenticate the transaction using EMV 3DS protocol (aka 3DS 2.1) only the following characters are allowed:&nbsp;
        </p>
        
        <ul>
          <li>
            A-Z, a-z, 0-9, "-"
          </li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

### &nbsp;

### <span lang="EN-US"><span>Credential-on-file Transactions</span></span>

<table class="Table">
  <tbody>
    <tr>
      <td>
        <span><span><strong><span lang="EN-US">Field&nbsp;</span></strong></span></span>
      </td>
      
      <td>
        <p>
          <span><span><strong><span lang="EN-US">Comment</span></strong></span></span>
        </p>
      </td>
    </tr>
    
    <tr>
      <td>
        <pre>
<span><span><span lang="EN-US">unscheduledCredentialOnFileType</span></span></span></pre>
      </td>
      
      <td>
        <p>
          <span><span><span lang="EN-US">This field allows you to flag transactions as unscheduled credential on file type. Currently the valid values are: FIRST, CARDHOLDER_INITIATED or MERCHANT_INITIATED to advise the type of transaction for these scenarios</span></span></span>
        </p>
      </td>
    </tr>
    
    <tr>
      <td>
        <pre>
<span lang="EN-US"><span>referencedSchemeTransactionId</span></span></pre>
      </td>
      
      <td>
        <span lang="EN-US"><span>This field allows you to include the payment scheme's transaction ID that has been returned in the response of the initial transaction (when credentials have been stored) in order to provide a reference to that original transaction</span></span>
      </td>
    </tr>
  </tbody>
</table>

&nbsp;

### <span><span><span><span><span><span><span><span><span><span><span><span><span><span><span><span><span><span>Purchasing Cards - Level II Data</span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span>

<table class="Table">
  <thead>
    <tr>
      <th>
        <p class="MsoBodyText">
          <span>Field</span>
        </p>
      </th>
      
      <th>
        &nbsp;
      </th>
      
      <th>
        <p class="MsoBodyText">
          <span>Comment</span>
        </p>
      </th>
    </tr>
  </thead>
  
  <tbody>
    <tr>
      <td>
        <pre class="MsoBodyText">
<span><span>pcCustomerReferenceID</span></span></pre>
      </td>
      
      <td>
        <span>&nbsp;</span>
      </td>
      
      <td>
        <p class="MsoBodyText">
          <span><span>Merchant-defined reference for the customer that will appear on the customer’s statement.</span></span>
        </p>
      </td>
    </tr>
    
    <tr>
      <td>
        <pre class="MsoBodyText">
<span><span>pcSupplierInvoiceNumber</span></span></pre>
      </td>
      
      <td>
        <span>&nbsp;</span>
      </td>
      
      <td>
        <p class="MsoBodyText">
          <span><span>Merchant-defined reference for the invoice – invoice number.</span></span>
        </p>
      </td>
    </tr>
    
    <tr>
      <td>
        <pre class="MsoBodyText">
<span><span>pcSupplierVATRegistrationNumber  </span></span></pre>
      </td>
      
      <td>
        <span>&nbsp;</span>
      </td>
      
      <td>
        <p class="MsoBodyText">
          <span><span>The ID number assigned by the tax authorities to the merchant.</span></span>
        </p>
      </td>
    </tr>
    
    <tr>
      <td>
        <pre class="MsoBodyText">
<span><span>pcTotalDiscountAmount</span></span></pre>
      </td>
      
      <td>
        <span>&nbsp;</span>
      </td>
      
      <td>
        <p class="MsoBodyText">
          <span><span>Total discount applied to a transaction (i.e. total transaction percentage discounts, fixed transaction amount reductions or summarization of line item discounts).</span></span>
        </p>
      </td>
    </tr>
    
    <tr>
      <td>
        <pre class="MsoBodyText">
<span><span>pcTotalDiscountRate</span></span></pre>
      </td>
      
      <td>
        <span>&nbsp;</span>
      </td>
      
      <td>
        <p class="MsoBodyText">
          <span><span>Rate of discount for the whole transaction.</span></span>
        </p>
      </td>
    </tr>
    
    <tr>
      <td>
        <pre class="MsoBodyText">
<span><span>pcVATShippingRate</span></span></pre>
      </td>
      
      <td>
        <span>&nbsp;</span>
      </td>
      
      <td>
        <p class="MsoBodyText">
          <span><span>Total shipping amount applied to the transaction. Merchants can choose to deliver contents of a single transaction in multiple shipments and this field reflects the total cost of those deliveries</span></span>
        </p>
      </td>
    </tr>
    
    <tr>
      <td>
        <pre class="MsoBodyText">
<span><span>pcVATShippingAmount</span></span></pre>
      </td>
      
      <td>
        <span>&nbsp;</span>
      </td>
      
      <td>
        <p class="MsoBodyText">
          <span><span>Total shipping amount applied to the transaction. Merchants can choose to deliver contents of a single transaction in multiple shipments and this field reflects the total cost of those deliveries</span></span>
        </p>
      </td>
    </tr>
    
    <tr>
      <td>
        <pre class="MsoBodyText">
<span><span>pcLineItemsJson</span></span></pre>
      </td>
      
      <td>
        <span>&nbsp;</span>
      </td>
      
      <td>
        <p class="MsoBodyText">
          <span><span>Line item details in JSON format. See table below.</span></span>
        </p>
      </td>
    </tr>
  </tbody>
</table>

<h5 class="MsoBodyText">
  <span><span><span><span><span><span><span><span><span><span><span><span><span><span><span><span><span><span>&nbsp;</span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span>
</h5>

<h3 class="MsoBodyText">
  <span><span><span><span><span><span><span><span><span><span><span><span><span><span><span><span><span><span>Purchasing Cards - Level III Data (line item details in JSON format)</span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span>
</h3>

<table class="Table">
  <thead>
    <tr>
      <th>
        <p>
          <span>Field</span>
        </p>
      </th>
      
      <th>
        &nbsp;
      </th>
      
      <th>
        <p>
          <span>Comment</span>
        </p>
      </th>
    </tr>
  </thead>
  
  <tbody>
    <tr>
      <td>
        <pre>
<span><span>CommodityCode</span></span></pre>
      </td>
      
      <td>
        <span>&nbsp;</span>
      </td>
      
      <td>
        <p>
          <span><span>Reference to a commodity code used to classify a purchased item.</span></span>
        </p>
      </td>
    </tr>
    
    <tr>
      <td>
        <pre>
<span><span>ProductCode</span></span></pre>
      </td>
      
      <td>
        <span>&nbsp;</span>
      </td>
      
      <td>
        <p>
          <span><span>Reference to a merchant product identifier – Universal Product Code (UPC) of a purchased item.</span></span>
        </p>
      </td>
    </tr>
    
    <tr>
      <td>
        <pre>
<span><span>Description</span></span></pre>
      </td>
      
      <td>
        <span>&nbsp;</span>
      </td>
      
      <td>
        <p>
          <span><span>Description of purchased item.</span></span>
        </p>
      </td>
    </tr>
    
    <tr>
      <td>
        <pre>
<span><span>Quantity</span></span></pre>
      </td>
      
      <td>
        <span>&nbsp;</span>
      </td>
      
      <td>
        <p>
          <span><span>Quantity of purchased items.</span></span>
        </p>
      </td>
    </tr>
    
    <tr>
      <td>
        <pre>
<span><span>UnitOfMeasure</span></span></pre>
      </td>
      
      <td>
        <span>&nbsp;</span>
      </td>
      
      <td>
        <p>
          <span><span>Unit of measure of purchased items.</span></span>
        </p>
      </td>
    </tr>
    
    <tr>
      <td>
        <pre>
<span><span>UnitPrice</span></span></pre>
      </td>
      
      <td>
        <span>&nbsp;</span>
      </td>
      
      <td>
        <p>
          <span><span>Mandatory data for Level III transactions.</span></span>
        </p>
      </td>
    </tr>
    
    <tr>
      <td>
        <pre>
<span><span>VATAmountAndRate</span></span></pre>
      </td>
      
      <td>
        <span>&nbsp;</span>
      </td>
      
      <td>
        <p>
          <span><span>Rate of the VAT amount e.g. 0.09 = 9%</span></span>
        </p>
      </td>
    </tr>
    
    <tr>
      <td>
        <pre>
<span><span>DiscountAmountAndRate         </span></span></pre>
      </td>
      
      <td>
        <span>&nbsp;</span>
      </td>
      
      <td>
        <p>
          <span><span>Rate of the discounted amount e.g. 0.09 = 9%</span></span>
        </p>
      </td>
    </tr>
    
    <tr>
      <td>
        <pre>
<span><span>LineItemTotal</span></span></pre>
      </td>
      
      <td>
        <span>&nbsp;</span>
      </td>
      
      <td>
        <p>
          <span><span>Calculation of the unit cost multiplied by the quantity and less the discount per line item. </span></span>
        </p>
        
        <p>
          <span><span>[Unit Cost * Quantity] – Discount per Line Item = Line Item Total.</span></span>
        </p>
      </td>
    </tr>
  </tbody>
</table>

##### <span><span><span><span><span><span><span><span><span><span><span><span><span><span><span><span><span><span>&nbsp;</span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span>

### <span><span><span><span><span><span><span><span><span><span><span><span><span><span><span><span><span><span><span><span><span><span>MCC 6012 Mandate in the UK</span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span>

<span><span><span><span><span><span><span><span><span><span><span><span><span><span><span><span><span><span><span><span><span>An MCC, or merchant category code, is a four-digit number assigned to a business by card companies. It is used to classify businesses by their goods or service offerings. In this particular instance, the merchant category code 6012 is for businesses who are classified as Financial Institutions.</span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span>

<p class="MsoBodyText">
  <span><span><span><span><span><span><span><span><span><span><span><span><span><span><span><span><span><span><span><span><span>For UK-based Financial Institutions with Merchant Category Code 6012, Visa and MasterCard have mandated additional information of the primary recipient of the loan to be included in the authorization message.</span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span>
</p>

<p class="MsoBodyText">
  <span><span><span><span><span><span><span><span><span><span><span><span><span><span><span><span><span><span><span><span><span>As per this mandate, you must use the following parameters for your transaction requests:</span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span>
</p>

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
        <pre>
<span><span><span><span>mcc6012BirthDay</span></span></span></span></pre>
      </td>
      
      <td>
        <span>&nbsp;</span>
      </td>
      
      <td>
        <p>
          <span><span><span><span><span>Recipient date of birth in format: dd.mm.yyy</span></span></span></span></span>
        </p>
      </td>
    </tr>
    
    <tr>
      <td>
        <pre>
<span><span><span><span>mcc6012AccountFirst6</span></span></span></span></pre>
      </td>
      
      <td>
        <span>&nbsp;</span>
      </td>
      
      <td>
        <span><span><span><span>First 6 digits of recipient PAN (where the primary recipient account is a card)</span></span></span></span>
      </td>
    </tr>
    
    <tr>
      <td>
        <pre>
<span><span><span><span>mcc6012AccountLast4</span></span></span></span></pre>
      </td>
      
      <td>
        <span>&nbsp;</span>
      </td>
      
      <td>
        <span><span><span><span>Last 4 digits of recipient PAN (where the primary recipient account is not a card)</span></span></span></span>
      </td>
    </tr>
    
    <tr>
      <td>
        <pre>
<span><span><span><span>mcc6012AccountNumber</span></span></span></span></pre>
      </td>
      
      <td>
        <span>&nbsp;</span>
      </td>
      
      <td>
        <span><span><span><span>Recipient account number (where the primary recipient account is not a card)</span></span></span></span>
      </td>
    </tr>
    
    <tr>
      <td>
        <pre>
<span><span><span><span>mcc6012Surname</span></span></span></span></pre>
      </td>
      
      <td>
        <span>&nbsp;</span>
      </td>
      
      <td>
        <span><span><span><span>Surname</span></span></span></span>
      </td>
    </tr>
    
    <tr>
      <td>
        <pre>
<span><span><span><span>mcc6012Zip</span></span></span></span></pre>
      </td>
      
      <td>
        <span>&nbsp;</span>
      </td>
      
      <td>
        <span><span><span><span>Post Code</span></span></span></span>
      </td>
    </tr>
  </thead>
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
        <pre>
dccInquiryId</pre>
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
        <pre>
numberOfInstallments</pre>
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
        <pre>
installmentsInterest</pre>
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
        <pre>
installmentDelayMonths  </pre>
      </td>
      
      <td>
        <pre>
&nbsp;</pre>
      </td>
      
      <td>
        This parameter allows you to delay the first instalment payment for several months, values 2-99 are currently possible.
      </td>
    </tr>
  </tbody>
</table>

### &nbsp;

### <span><span><span><span><span><span><span><span><span><span><span><span><span><span><span><span><span><span>Information Required For Specific Payment Methods</span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span>

&nbsp;

##### <span><span><span><span><span><span><span><span><span><span><span><span><span><span><span><span><span><span>SEPA Direct Debit</span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span>

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
        <pre>
<span>mandateDate</span></pre>
      </td>
      
      <td>
        <span>&nbsp;</span>
      </td>
      
      <td>
        <p>
          <span><span>This field allows you to reference to the date of the original mandate when performing recurring Direct Debit transactions. The date needs to be submitted in format YYYYMMDD. Please note that this is a mandatory field for recurring Direct Debit transactions.</span></span>
        </p>
      </td>
    </tr>
    
    <tr>
      <td>
        <pre>
<span>mandateReference</span></pre>
      </td>
      
      <td>
        <span>&nbsp;</span>
      </td>
      
      <td>
        <span>This field allows you to transmit a Mandate Reference for Direct Debit payments. Please note the regulatory requisite to keep the Mandate Reference unambiguous.</span>
      </td>
    </tr>
    
    <tr>
      <td>
        <pre>
<span>mandateType</span></pre>
      </td>
      
      <td>
        <span>&nbsp;</span>
      </td>
      
      <td>
        <span>This field allows you to process Direct Debit transactions that are based on mandates for recurring collections. The mandate type can be set to ‘single’ for single (one-off) debit collections, to ‘firstCollection’ when submitting the initial transaction related to a mandate for recurring Direct Debit collections, to ‘recurringCollection’ for subsequent recurring transactions or to ‘finalCollection’ for the last direct debit in a series of recurring direct debits. Transactions where this parameter is not submitted by the merchant will be flagged as a single debit collection.<br /> Please note that it is mandatory to submit a mandateReference in case of recurring collections.</span>
      </td>
    </tr>
    
    <tr>
      <td>
        <pre>
<span>mandateUrl</span></pre>
      </td>
      
      <td>
        <span>&nbsp;</span>
      </td>
      
      <td>
        <span>When your store is enabled for SEPA Direct Debit as part of the Local Payments offering, this field allows you to transmit a valid URL of SEPA Direct Debit mandate to enable the Risk and Compliance department to access the details.<br /> Please note that it is mandatory to submit a mandateReference and a mandateDate together with a mandateUrl in case you manage SEPA Direct Debit mandates on your side in the combination with the Local Payments offering.</span>
      </td>
    </tr>
  </thead>
</table>

##### <span><span><span><span><span><span><span><span><span><span><span><span><span><span><span><span><span><span>&nbsp;</span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span>

##### <span><span><span><span><span><span><span><span><span><span><span><span><span><span><span><span><span><span>MasterPass</span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span>

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
        <pre>
<span>reviewOrder</span></pre>
      </td>
      
      <td>
        <span>&nbsp;</span>
      </td>
      
      <td>
        <p>
          <span><span>MasterPass-specific parameter for scenarios where the final amount needs to be confirmed by the customer after returning from the Wallet. Set the value for this parameter to ‘true’ in order to indicate that the final transaction amount needs to be reviewed by the cardholder.</span></span>
        </p>
      </td>
    </tr>
    
    <tr>
      <td>
        <pre>
<span>reviewURL</span></pre>
      </td>
      
      <td>
        <span>&nbsp;</span>
      </td>
      
      <td>
        <span>MasterPass-specific parameter for scenarios where the final amount needs to be confirmed by the customer after returning from the MasterPass environment. Use this parameter to indicate where the customer shall be redirected to in order to review and complete the transaction after having clicked on “Finish shopping” within the Wallet.</span>
      </td>
    </tr>
  </thead>
</table>

##### <span><span><span><span><span><span><span><span><span><span><span><span><span><span><span><span><span><span>&nbsp;</span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span>

##### <span><span><span><span><span><span><span><span><span><span><span><span><span><span><span><span><span><span>China Domestic Payments</span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span>

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
        <pre>
<span>item1</span></pre>
      </td>
      
      <td>
        <span>&nbsp;</span>
      </td>
      
      <td>
        <p>
          <span><span><span><span><span><span>Submit exactly one line item parameter with four (4) property values in the following format:&nbsp;id;description;quantity;item_total_price</span></span></span></span></span></span>
        </p>
        
        <p>
          <span><span><span><span><span><span>Transaction request without a line item or with multiple line items will be declined.&nbsp;<br /> Example: 100018;The Hobbit;1;3.50</span></span></span></span></span></span>
        </p>
        
        <table>
          <tbody>
            <tr>
              <td>
                <span><span><span><span><span><span><span><span>Position</span></span></span></span></span></span></span></span>
              </td>
              
              <td>
                <span><span><span><span><span><span><span><span>Property</span></span></span></span></span></span></span></span>
              </td>
              
              <td>
                <span><span><span><span><span><span><span><span>Description</span></span></span></span></span></span></span></span>
              </td>
            </tr>
            
            <tr>
              <td>
                <span><span><span><span><span><span><span><span>1</span></span></span></span></span></span></span></span>
              </td>
              
              <td>
                <span><span><span><span><span><span><span><span>id</span></span></span></span></span></span></span></span>
              </td>
              
              <td>
                <p>
                  <span><span><span><span><span><span><span><span><span>Product code (编码Code)</span></span></span></span></span></span></span></span></span>
                </p>
                
                <p>
                  <span><span><span>>&nbsp;<a href="https://docs.firstdata.com/org/gateway/node/401">See valid values here</a></span></span></span>
                </p>
              </td>
            </tr>
            
            <tr>
              <td>
                <span><span><span><span><span><span><span><span>2</span></span></span></span></span></span></span></span>
              </td>
              
              <td>
                <span><span><span><span><span><span><span><span>description</span></span></span></span></span></span></span></span>
              </td>
              
              <td>
                <span><span><span><span><span><span><span><span>Product name</span></span></span></span></span></span></span></span>
              </td>
            </tr>
            
            <tr>
              <td>
                <span><span><span><span><span><span><span><span>3</span></span></span></span></span></span></span></span>
              </td>
              
              <td>
                <span><span><span><span><span><span><span><span>quantity</span></span></span></span></span></span></span></span>
              </td>
              
              <td>
                <span><span><span><span><span><span><span><span>Quantity of product(s)</span></span></span></span></span></span></span></span>
              </td>
            </tr>
            
            <tr>
              <td>
                <span><span><span><span><span><span><span><span>4</span></span></span></span></span></span></span></span>
              </td>
              
              <td>
                <span><span><span><span><span><span><span><span>item_total_price</span></span></span></span></span></span></span></span>
              </td>
              
              <td>
                <span><span><span><span><span><span><span><span>Price of product(s)</span></span></span></span></span></span></span></span>
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
        <pre>
<span><span><span>customerid</span></span></span></pre>
      </td>
      
      <td>
        <span>&nbsp;</span>
      </td>
      
      <td>
        <p>
          <span><span><span><span>Unique reference to identify the consumer</span></span></span></span>
        </p>
      </td>
    </tr>
    
    <tr>
      <td>
        <pre>
<span lang="EN-US"><span>custom_domesticBankId    </span></span></pre>
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        <span lang="EN-US"><span>Submit a bank identifier for reporting purpose in relation to promotions with local Chinese banks. Max length 8.</span></span>
      </td>
    </tr>
  </thead>
</table>

##### &nbsp;

##### <span><span><span><span><span><span><span><span><span><span><span><span><span><span><span><span><span><span>Korea Domestic Payments</span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span></span>

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
        <pre>
<span><span><span>checkoutoption     </span></span></span></pre>
      </td>
      
      <td>
        <span>&nbsp;</span>
      </td>
      
      <td>
        <p>
          <span><span>Set this parameter to&nbsp;‘combinedpage’ for Korea domestic payments</span></span>
        </p>
      </td>
    </tr>
    
    <tr>
      <td>
        <pre>
<span><span><span>oid</span></span></span></pre>
      </td>
      
      <td>
        <span>&nbsp;</span>
      </td>
      
      <td>
        <span><span>Unique order ID, alphanumeric string (32 max) </span></span>
      </td>
    </tr>
    
    <tr>
      <td>
        <pre>
<span><span>customParam_kps_ItemInfo  </span></span></pre>
      </td>
      
      <td>
        <span>&nbsp;</span>
      </td>
      
      <td>
        <p>
          <span><span><span>Type of purchased item, alphanumeric string (1 max)</span></span></span>
        </p>
        
        <p>
          <span><span><span>Possible values are:</span></span></span>
        </p>
        
        <p>
          <span><span><span>"1": Goods</span></span></span><br /> <span><span><span>"2": Online content</span></span></span>
        </p>
      </td>
    </tr>
    
    <tr>
      <td>
        <pre>
<span><span>customParam_kps_CcProdDesc </span></span></pre>
      </td>
      
      <td>
        <span>&nbsp;</span>
      </td>
      
      <td>
        <span><span>Description of purchased items to be displayed on the KPS payment page, alphanumeric string (256 max)</span></span>
      </td>
    </tr>
  </thead>
</table>
