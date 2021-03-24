---
title: Completion (Post-Authorization)
author: steffen.dangel@firstdata.de
---

## Step 3: Completion When Goods Get Shipped

If you have used the transaction type Pre-Authorization when your customer checked out in your webshop, funds have been reserved on the customer's card account but have not been transferred to your account yet.

In order to complete a transaction and initiate the settlement process, you will need to send a Post-Authorization (postauth) via our API or intiate the completion manually using our Virtual Terminal.

> [See our API Reference on how to create a postauth][1]

> [Trigger the completion manually][2]

&nbsp;

 [1]: http://test-ndpfdc.pantheonsite.io/org/gateway/docs/api#post-authorization-capture
 [2]: http://test-ndpfdc.pantheonsite.io/org/gateway/node/34
