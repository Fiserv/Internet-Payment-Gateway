Return (aka Refund)
---

## Step 5: Giving Money Back When Goods Have Been Returned

If you want to return funds to a customer's card against an existing order, you can use the Order ID as a reference so that you do not need to submit card details for this activity. You can return the full amount of the order or a partial amount.

&nbsp;

### Initiate a Return Using the API

There are two options to initiate a Return using the API:

<table>
  <tbody>
    <tr>
      <td>
        <img alt="/orders/{order-id}" data-align="left" data-entity-type="file" data-entity-uuid="e0a54d19-c669-477a-a300-23fd1e897dd0" src="/files/POST-orders.png" />
      </td>
      
      <td>
        &nbsp; &nbsp; &nbsp;
      </td>
      
      <td>
        <p>
          Use&nbsp;<em>/orders</em> and the Order ID&nbsp;to reference to the order where you want to perform a full or partial refund&nbsp;and include the amount and currency to be returned in the payload
        </p>
      </td>
    </tr>
    
    <tr>
      <td>
        <img alt="/payments/{transaction-id}" data-align="left" data-entity-type="file" data-entity-uuid="839e5178-1612-4817-bc7c-40e39d9708d0" src="/files/POST-payments_1.png" />
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        Use&nbsp;<em>/payments</em> and the Transaction ID&nbsp;(<em>ipgTransactionId</em>&nbsp;or&nbsp;<em>merchantTransactionId</em>) if you want to send a full or partial refund for a specific transaction&nbsp;and include the amount and currency to be returned in the payload
      </td>
    </tr>
  </tbody>
</table>

##### &nbsp;

##### REST API Request Example

<table>
  <tbody>
    <tr>
      <td>
        <pre>
{
  "requestType": "ReturnTransaction",
&nbsp; "transactionAmount": {
    "total": "20.00",
    "currency": "USD"
  }
}</pre>
      </td>
    </tr>
  </tbody>
</table>

> [REST API Reference][1]&nbsp;

&nbsp;

## Run a Return Manually Using the Virtual Terminal

### Basic Return From Transaction Report

Should you wish to perform a basic return (without needing to add any additional information to the transaction) you can do so from the Transaction report.

Firstly find the transaction you wish to perform a return on in the report and select to open up the full order details.

<img alt="Find Transaction" data-align="center" data-entity-type="file" data-entity-uuid="6c4b608b-6eb4-485c-a1f1-81f06417be58" height="561" src="/sites/default/files/inline-images/from%20report.png" width="552" /> 

Enter the amount you wish to return in the Return Order box

<img alt="From Report 1" data-align="center" data-entity-type="file" data-entity-uuid="2ea2852e-4a93-4132-8649-fb2637812ae4" height="206" src="/sites/default/files/inline-images/from%20report%201.png" width="533" /> 

Select 'Return Order' once you have entered the amount to be returned and you will be presented with the&nbsp;Credit Order Result.&nbsp;

<img alt="From Report 2" data-align="center" data-entity-type="file" data-entity-uuid="66dadb98-a6ab-433c-9665-978071dba62f" height="158" src="/sites/default/files/inline-images/from%20report%202.png" width="545" /> 

### &nbsp;

### Return with Option to Add Further Details&nbsp;

To perform a Return whereby you wish to add detail to the transaction, first go to the Virtual Terminal's Return page.

<img alt="Start Return" data-align="center" data-entity-type="file" data-entity-uuid="eb53c69d-a370-4346-a34a-b84e6c82bf9c" height="133" src="/sites/default/files/inline-images/Return%20Start.jpg" width="493" /> 

A page will appear, with a field for the order number. If you don’t know your order number, you can find it in your Reports.

<img alt="Enter Order Number" data-align="center" data-entity-type="file" data-entity-uuid="13cc9feb-1447-4201-be59-d021c61c6003" height="143" src="/sites/default/files/inline-images/Return%202.png" width="502" /> 

Once you’ve located the order number, enter it in the input box and then click on the Retrieve Order button. A page will appear showing all the existing information from that order.

<img alt="Order Shown" data-align="center" data-entity-type="file" data-entity-uuid="190a3b79-97ad-42d9-8607-41cbf14ac305" height="324" src="/sites/default/files/inline-images/Return%204.png" width="501" /> 

Review these fields to ensure you have selected the correct order. (You may have to expand some of the sections at the bottom of the page to see all the fields.) If this isn’t the right order, click on your browser's Back button to return to the previous page and retrieve an alternate order.

If this is the correct order, enter the amount to return in the appropriate fields. By default, the fields will be pre-filled with the total amount available to be returned. It is possible to return a lower amount than the order total, to do so make corrections as appropriate ensuring the sum of the subtotal, tax and shipping amount equal the Total amount; if it doesn’t, you will get an error when you click the 'Continue' button.

Once you’ve finished with the Order fields, change any other fields related to the Customer Contact Information, Payment Information, or Comments, then click the 'Continue' button.

<img alt="Enter Return Info" data-align="center" data-entity-type="file" data-entity-uuid="ba143a2b-727a-4aa0-b755-2982e4619087" height="431" src="/sites/default/files/inline-images/Return%205.png" width="520" /> 

Once you click the 'Continue' button, if all entries in the form were valid, another page will appear asking you to confirm the information.

If everything is okay, click on the 'Submit' button; otherwise, click on the Back button to make the appropriate changes. (If any fields are missing or incorrect, the Return page will reappear with an error message at the top and the incorrect/missing fields flagged with an error graphic.) Make the appropriate changes then click the 'Continue' button again. A confirmation page should appear.

Review the information and then click the 'Submit' button.

A final Transaction Results page will appear, indicating whether the transaction was approved or declined and reiterating all the transaction information.

<img alt="Return Confirmation" data-align="center" data-entity-type="file" data-entity-uuid="cda56106-8cfb-4a0f-9a2c-7722dee2eed0" height="520" src="/sites/default/files/inline-images/Return%207.png" width="515" /> 

In case you are using the Virtual Terminal functionality to trigger a return for a SOFORT Banking transaction please be informed that due to specifics of this payment method, the transaction is only marked as being prepared for refund, but not yet executed. In order for your customer to receive the money, you need to execute the return transaction via SOFORT’s merchant portal or via their API.&nbsp;<span lang="EN-US"><span>Please note that this is not applicable when processing SOFORT through the Fiserv Local Payments offering.</span></span>

###  
&nbsp;

 [1]: https://docs.firstdata.com/org/gateway/docs/api
