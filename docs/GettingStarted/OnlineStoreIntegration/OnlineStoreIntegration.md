---
title: Online Store Integration
author: steffen.dangel@firstdata.de
---

The easiest first step for adding payments capabilities to your website is to implement a HTTP form that you post to our Gateway URL.

This type of integration allows you to let our Gateway manage the customer redirections that are required in the checkout process of many payment methods or authentication mechanisms and gives you the option to use&nbsp; secure hosted pages or an embeddable form which can reduce the burden of compliance with the Data Security Standard of the Payment Card Industry (PCI DSS).

For the steps where no direct consumer interaction is required, it's best to use our API.

The following five steps provide an overview of a standard online store integration with links to alternative options where applicable:

##### > Step 1: [Checkout Process in Your Webstore (Pre-Authorization or Sale)][1]  
> Step 2: [Receiving the Transaction Result][2]  
> Step 3: [Completion When Goods Get Shipped (Post-Authorization)][3]  
> Step 4: [Voiding a Transaction][4]  
> Step 5: [Giving Money Back When Goods Have Been Returned (Refund)][5]

 [1]: http://test-ndpfdc.pantheonsite.io/org/gateway/node/331
 [2]: http://test-ndpfdc.pantheonsite.io/org/gateway/node/315
 [3]: http://test-ndpfdc.pantheonsite.io/org/gateway/node/318
 [4]: http://test-ndpfdc.pantheonsite.io/org/gateway/node/319
 [5]: http://test-ndpfdc.pantheonsite.io/org/gateway/node/223
