Online Store Integration
---

#### Adding Payment Capabilities to a Website

The easiest way to add payment&nbsp;capabilities to your website is to implement a HTML form that you post to our Gateway URL.

This type of integration allows you to let our Gateway manage the customer redirections that are required in the checkout process of many payment methods or authentication mechanisms and gives you the option&nbsp;to use&nbsp;secure hosted pages which can reduce the burden of compliance with the Data Security Standard of the Payment Card Industry (PCI DSS).

#### Application Programming Interface

For&nbsp;steps where no direct consumer interaction is required and no sensitive cardholder data is getting processed, it's best to use our [Application Programming Interface (API)][1]. Please note that if you plan to collect your customer's card details within your environment and send it to our API, you must ensure that your system components are PCI DSS compliant.

#### Key Steps

The following five steps provide an overview of a standard online store integration with links to alternative options where applicable:

##### > Step 1: [Checkout Process in Your Webstore (Pre-Authorization or Sale)][2]  
&nbsp;

##### > Step 2: [Receiving the Transaction Result][3]  
&nbsp;

##### > Step 3: [Completion When Goods Get Shipped (Post-Authorization)][4]  
&nbsp;

##### > Step 4: [Voiding a Transaction][5]  
&nbsp;

##### > Step 5: [Giving Money Back When Goods Have Been Returned (Refund)][6]

 [1]: https://docs.firstdata.com/org/gateway/docs/api
 [2]: http://docs.firstdata.com/org/gateway/node/321
 [3]: http://docs.firstdata.com/org/gateway/node/315
 [4]: http://docs.firstdata.com/org/gateway/node/318
 [5]: http://docs.firstdata.com/org/gateway/node/319
 [6]: http://docs.firstdata.com/org/gateway/node/223
