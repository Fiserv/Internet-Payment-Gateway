### Void
---

## Step 4: Voiding a Transaction

If your customer has canceled the order or you detect&nbsp;suspicious order details, you can void the transaction referencing the original Transaction ID.

<table>
  <tbody>
    <tr>
      <td>
        <img alt="/payments/{transaction-id}" data-entity-type="file" data-entity-uuid="e594284a-706d-4b4a-b448-f6747c4e3a52" src="/files/POST-payments_0.png" />
      </td>
      
      <td>
        &nbsp; &nbsp; &nbsp; &nbsp;
      </td>
      
      <td>
        <p>
          Use&nbsp;<em>/payments</em> and the Transaction ID (<em>ipgTransactionId</em> or <em>merchantTransactionId</em>)&nbsp;to reference to the specific transaction that you want to void.
        </p>
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
  "requestType": "VoidTransaction"
}</pre>
      </td>
    </tr>
  </tbody>
</table>

> [REST API Reference][1]&nbsp;

 [1]: https://docs.firstdata.com/org/gateway/docs/api
