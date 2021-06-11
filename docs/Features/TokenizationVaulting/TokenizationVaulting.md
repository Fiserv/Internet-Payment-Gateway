Tokenization/Vaulting
---

If you need sensitive cardholder data for future use (e.g. to allow&nbsp;one-click shopping for registered customers or to trigger subsequent transactions), you can use a token to reference to the data at a later point so that you do not need to store these details within your own systems.

If you use a HTML form to initiate the payment, you can use the following functions:

###  
Store or update payment information when performing a transaction

Additionally send the parameter `hosteddataid` together with the transaction data as a unique identification for the payment information in this transaction.

Depending on the payment type, credit card number and expiry date or IBAN and BIC will be stored under this ID if the transaction has been successful. In cases where the submitted `hosteddataid` already exists for your store, the stored payment information will be updated.

If you want to assign multiple IDs to the same payment information record, you can submit the parameter `hosteddataid` several times with different values in the same transaction.

If you prefer not to assign a token yourself but want to let the gateway do this for you, send the parameter `assignToken` and set it to ‘true’. The gateway will then assign a token and include it in the transaction response as `hosteddataid`.

If you have use cases where you need some of the tokens for single transactions only (e.g. for consumers that check out as a “guest”, use the additional parameter ‘tokenType’ with the values ‘ONETIME’ (card details will only be stored for a short period of time) or ‘MULTIPAY’ (card details will be stored for use in future transactions).

&nbsp;

###  
Initiate payment transactions using stored data

If you stored cardholder information using the Data Vault option, you can perform transactions using the `hosteddataid` without the need to pass the credit card or bank account data again.

Please note that it is not allowed to store the card code (in most cases on the back of the card) so that for credit card transactions, the cardholder still needs to enter this value. If you use First Data’s hosted payment forms, the cardholder will see the last four digits of the stored credit card number, the expiry date and a field to enter the card code.

When using multiple Store IDs, it is possible to access stored card data records of a different Store ID then the one that has been used when storing the record. In that way you can for example use a shared data pool for different distributive channels. To use this feature, submit the Store ID that has been used when storing the record as the additional parameter `hosteddatastoreid`.

When using the **REST API** for a subsequent transaction with the stored card details, include the following parameters in order to reference back to the original authorization and cardholder authentication where applicable:

<table>
  <tbody>
    <tr>
      <td>
        <pre>
<strong>paymentToken</strong></pre>
      </td>
      
      <td>
        &nbsp; &nbsp;
      </td>
      
      <td>
        &nbsp;
      </td>
    </tr>
    
    <tr>
      <td>
        <pre>
value</pre>
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        <p>
          Include the token that you have defined or obtained when tokenizing the customer's card details (<code>hosteddataid</code>)
        </p>
      </td>
    </tr>
    
    <tr>
      <td>
        <pre>
<strong>storedCredentials</strong></pre>
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        &nbsp;
      </td>
    </tr>
    
    <tr>
      <td>
        <pre>
sequence</pre>
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        Set this to "SUBSEQUENT" in order to indicate that this is not the first transaction with this customer but one of many transactions that you submit on their behalf after you had obtained the customer's consent to store the card details for future use. If it is the first transaction with these card details, set this to "FIRST".
      </td>
    </tr>
    
    <tr>
      <td>
        <pre>
scheduled</pre>
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        Set this to 'false' in order to indicate that this is an unscheduled transaction, i.e not a recurring transaction at a regular interval.
      </td>
    </tr>
    
    <tr>
      <td>
        <pre>
referencedSchemeTransactionId</pre>
      </td>
      
      <td>
        &nbsp; &nbsp; &nbsp;
      </td>
      
      <td>
        If you received a Scheme Transaction ID in the response to your original authorization (e.g. a zero-value authorization when storing the card details), include this reference in order to link back the transaction to the original agreement.
      </td>
    </tr>
    
    <tr>
      <td>
        <pre>
initiator</pre>
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        Set this to "MERCHANT" in order to indicate that you initiated this transaction with no direct involvement of the customer. If you are using the stored card details for a 1-click payment scenario where the cardholder is involved but you want to allow them to check out without the need to enter their card details again, set this to "CARDHOLDER".
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
  "transactionAmount": {
    "total": "12.00",
    "currency": "EUR"
  },
  "requestType": "PaymentTokenSaleTransaction",
  "paymentMethod": {
    "paymentToken": {
      "value": "12345",
    }
  },
  "storedCredentials": {
    "sequence": "SUBSEQUENT",
    "scheduled": false
    "referencedSchemeTransactionId": "098765432112345"
    "initiator": "CARDHOLDER",
  }
}</pre>
      </td>
    </tr>
  </tbody>
</table>

> [REST API Reference][1]&nbsp;

### &nbsp;

### Avoid duplicate cardholder data for multiple records

To avoid customers using the same cardholder data for multiple user accounts, the additional parameter `declineHostedDataDuplicates` can be sent along with the request. The valid values for this parameter are ‘true’/’false’. If the value for this parameter is set to ‘true’ and the cardholder data in the request is already found to be associated with another `hosteddataid`, the transaction will be declined.

 [1]: https://docs.firstdata.com/org/gateway/docs/api
