---
title: Completion (Post-Authorization)
---

## Step 3: Completion When Goods Get Shipped

If you have used the transaction type Pre-Authorization when your customer checked out in your webshop, funds have been reserved on the customer's card account but have not been transferred to your account yet.

In order to complete a transaction and initiate the settlement process, you will need to send a Post-Authorization (_postauth_) via our API or initiate the completion manually using our Virtual Terminal.

&nbsp;

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
          Use&nbsp;<em>/orders</em> and the Order ID&nbsp;to reference to the order with the pre-authorized balance
        </p>
      </td>
    </tr>
    
    <tr>
      <td>
        <img alt="/payments/{transaction-id}" data-entity-type="file" data-entity-uuid="e594284a-706d-4b4a-b448-f6747c4e3a52" src="/files/POST-payments_0.png" />
      </td>
      
      <td>
        &nbsp;&nbsp;
      </td>
      
      <td>
        Use&nbsp;<em>/payments</em> and the Transaction ID (<em>ipgTransactionId</em>&nbsp;or&nbsp;<em>merchantTransactionId</em>) if you want to reference to a specific pre-authorization transaction that you want to complete
      </td>
    </tr>
  </tbody>
</table>

&nbsp;

##### REST API Request Example

<table>
  <tbody>
    <tr>
      <td>
        <pre>
{
  "requestType": "PostAuthTransaction",
&nbsp; "transactionAmount": {
    "total": "28.59",
    "currency": "GBP"
  }
}</pre>
      </td>
    </tr>
  </tbody>
</table>

> [REST API Reference][1]&nbsp;

 [1]: https://docs.firstdata.com/org/gateway/docs/api
