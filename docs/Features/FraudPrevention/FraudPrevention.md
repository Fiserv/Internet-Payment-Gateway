Fraud Prevention
---

<span><span><span><span><span><span><span><span><span>There are several ways that our gateway can help you to prevent fraud from interfering with your business success:</span></span></span></span></span></span></span></span></span>

  * <span><span><span><span><span><span><span><span><strong><span>Fraud Detect </span></strong></span></span></span><span><span><span><span>- a comprehensive fraud prevention solution with real-time fraud scoring and machine learning capabilities designed to reduce a merchant’s overall exposure and cost of fraud.</span></span></span></span></span></span></span></span></span>
  * <span><span><span><span><span><span><strong>Blocking</strong> - </span></span></span></span></span></span>the capability to block credit card numbers, names, domain names, and IP or Class C addresses from purchasing at their store
  * <span><span><span><span><span><span><strong>Maximum Purchase Limit</strong> - </span></span></span></span></span></span>the power to set a limit on the maximum purchase that can be made at your store
  * <span><span><span><span><span><span><strong>Auto Lockout and Duplicate Lockout</strong> - </span></span></span></span></span></span>&nbsp;the ability to set auto lockout and duplicate <span><span><span><span><span><span><span><span><span>lockout times.</span></span></span></span></span></span></span></span></span>
  * **<span><span><span><span><span><span>Country Profiles</span></span></span></span></span></span>**

&nbsp;

### <span><span><span><span><span><span>Fraud Detect Process Flow</span></span></span></span></span></span>

_The following information is only relevant if you are using Fiserv's Fraud Detect solution._

  1. <span><span lang="EN"><span><span>You send a payment transaction request to our gateway and it gets routed for authorization</span></span></span></span>
  2. <span><span lang="EN"><span><span>The gateway receives the authorization response (approved/declined) including details like if the card code matched or if the address has been succesfully verified.</span></span></span></span>
  3. <span><span lang="EN"><span><span>If approval is received, the gateway submits all transaction details and authorization results to the Fraud Detect scoring engine.</span></span></span></span>
  4. <span><span lang="EN"><span><span>The gateway receives the response from Fraud Detect with the fraud score (between 1-1000)</span></span></span></span>
  5. <span><span lang="EN"><span><span>Depending on how the risk tolerance level is set for your Store (default 500), you will either receive a an approved result back from the gateway or the gateway will automatically void the previous authorization and send you a decline back. The response to your systems includes the fraud score.</span></span></span></span>

<span lang="EN"><span><span>It is possible to amend the scoring at which&nbsp;you wish a transaction to be Approved or Declined at by using a slider provided in the Fraud Settings section of the Administration tab of the <a href="http://docs.firstdata.com/org/gateway/node/139">Virtual Terminal</a>.</span></span></span>

### &nbsp;

### Fraud Detect Integration

_The following information is only relevant if you are using the Fiserv's Fraud Detect solution._

The information required to be forwarded to Fraud Detect to obtain a fraud score is pulled from both your merchant master data and the information sent to perform the transaction. If you use a HTML form to initiate the transaction and want to pass additional details for the scoring such as mobile device information, you can include these values as custom parameters, e.g.

  * <span><span><span><span lang="EN-US">customParam_deviceRiskId </span></span></span></span>
  * <span><span><span><span lang="EN-US">customParam_deviceRiskAPIKey </span></span></span></span>
  * <span><span><span><span lang="EN-US">customParam_deviceRiskHost</span></span></span></span>

<span lang="EN-US">Example:</span>

<pre><span lang="EN-US"><span>&lt;input type="hidden" name="customParam_deviceRiskId" value="*****"/&gt;</span></span></pre>

<span lang="EN-US"><span>The gateway then passes these parameters on to Fraud Detect.</span></span>
