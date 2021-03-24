---
title: Return (aka Refund)
author: steffen.dangel@firstdata.de
---

## Step 5: Giving Money Back When Goods Have Been Returned

If you want to return funds to a customer's card against an existing order, you can use the Order ID as a reference so that you do not need to submit card details for this activity. You can return the full amount of the order or a partial amount.

> [See how to create the API request for a Return][1]

&nbsp;

### Run a Return Manually Using the Virtual Terminal

  1. To do a Return, first go to the Virtual Terminal's Return page. A page will appear, with a field for the order number. If you don’t know your order number, you can find it in your Reports.
  2. Once you’ve located the order number, enter it in the input box, then click on the Retrieve Order button. A page will appear showing all the existing information from that order.
  3. Review these fields to ensure you have selected the correct order. (You may have to expand some of the sections at the bottom of the page to see all the fields you need to see.) If this isn’t the right order, click on your browser's Back button to return to the previous page and retrieve an alternate order.
  4. If this is the correct order, enter the amount to return in the appropriate fields. By default, the fields will be pre-filled with the total amount available to be returned. It is possible to return a lower amount than the order total, to do so make corrections as appropriate ensuring the sum of the subtotal, tax and shipping amount must equal the Total amount; if it doesn’t, you will get an error when you click the Continue button.
  5. Once you’ve finished with the Order fields, change any other fields related to Customer Contact Information, Payment Information, or Comments, then click the Continue button.
  6. Once you click the Continue button, if all entries in the form were valid, another page will appear asking you to confirm the information.
  7. If everything is okay, click on the Submit button; otherwise, click on the Back button to make the appropriate changes. (If any fields are missing or incorrect, the Return page will reappear with an error message at the top and the incorrect/missing fields flagged with an error graphic. Make the appropriate changes then click the Continue button again. A confirmation page should appear. Review the information, then click the Submit button.
  8. A final Transaction Results page will appear, indicating whether the transaction was approved or declined and reiterating all the transaction information.

In case you are using the Virtual Terminal functionality to trigger a return for a SOFORT Banking transaction please be informed that due to specifics of this payment method, the transaction is only marked as being prepared for refund, but not yet executed. In order for your customer to receive the money, you need to execute the return transaction via SOFORT’s merchant portal or via their API.

 [1]: http://test-ndpfdc.pantheonsite.io/org/gateway/docs/api#return-refund
