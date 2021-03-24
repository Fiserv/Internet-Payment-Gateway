---
title: Hosted Payment Pages
author: steffen.dangel@firstdata.de
---

If you want to fully outsource the payment process in order not to have any sensitive cardholder data on your systems, you can use our ready-made hosted pages for your customers to enter their payment information.

The hosted pages show your merchant name at the top and allow you to display a summary of the purchased items to your customer.

### Required Fields

In addition to the [fields that are mandatory for every payment request][1] that you initiate through a HTML form, the following fields are required for the hosted payment page integration:

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
        For the hosted payment page integration, set the value for this parameter to <em>combinedpage</em>
      </td>
    </tr>
  </tbody>
</table>

&nbsp;

By not including fields like e.g. the card number or expiry date in your request for a card payment, the gateway takes your customer to a secure page to enter that information.

If you do not want to let your customer select the payment method on the hosted page but want to handle that part upfront within your shop environment, you can submit the [payment method][2] in your request.

### Optional Fields

> [Billing/Shipping fields][3]  
> [Other optional fields][4]

&nbsp;

 [1]: http://test-ndpfdc.pantheonsite.io/org/gateway/node/90
 [2]: http://test-ndpfdc.pantheonsite.io/org/gateway/node/55
 [3]: http://test-ndpfdc.pantheonsite.io/org/gateway/node/212
 [4]: http://test-ndpfdc.pantheonsite.io/org/gateway/node/224
