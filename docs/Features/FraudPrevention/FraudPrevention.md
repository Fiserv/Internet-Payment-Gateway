---
title: Fraud Prevention
author: jill.oliver@firstdata.com
---

<span><span><span><span><span><span><span><span><span>There are several ways that the First Data Gateway can help you to prevent fraud from interfering with your business success:</span></span></span></span></span></span></span></span></span>

  * <span><span><span><span><span><span><span><span><strong><span>Fraud Detect </span></strong></span></span></span><span><span><span><span>- a comprehensive fraud prevention solution with real-time fraud scoring and machine learning capabilities designed to reduce a merchant’s overall exposure and cost of fraud.</span></span></span></span></span></span></span></span></span>
  * <span><span><span><span><span><span><strong>Blocking</strong> - </span></span></span></span></span></span>the capability to block credit card numbers, names, domain names, and IP or Class C addresses from purchasing at their store
  * <span><span><span><span><span><span><strong>Maximum Purchase Limit</strong> - </span></span></span></span></span></span>the power to set a limit on the maximum purchase that can be made at your store
  * <span><span><span><span><span><span><strong>Auto Lockout and Duplicate Lockout</strong> - </span></span></span></span></span></span>&nbsp;the ability to set auto lockout and duplicate <span><span><span><span><span><span><span><span><span>lockout times.</span></span></span></span></span></span></span></span></span>
  * **<span><span><span><span><span><span>Country Profiles</span></span></span></span></span></span>**

### &nbsp;

### Fraud Detect Integration

_The following information is only relevant if you are using the First Data Fraud Detect solution._

The information required to be forwarded to Fraud Detect to obtain a fraud score is pulled from both your merchant master data and the information sent to perform the transaction. The only addition will be if you want to pass mobile device details to be included in the scoring.

<span lang="EN-US">In&nbsp;this case&nbsp;the below additional information needs to be passed these with the following parameter naming:</span>

  * <span><span><span><span lang="EN-US">customParam_deviceRiskId </span></span></span></span>
  * <span><span><span><span lang="EN-US">customParam_deviceRiskAPIKey </span></span></span></span>
  * <span><span><span><span lang="EN-US">customParam_deviceRiskHost</span></span></span></span>

<span lang="EN-US">Example:</span>

<pre><span lang="EN-US"><span>&lt;input type="hidden" name="customParam_deviceRiskId" value="*****"/&gt;</span></span></pre>

<span lang="EN-US"><span>These fields are handled in the same way as other optional request parameters. The gateway stores these parameters and passes them on to Fraud Detect. These parameters have no impact on the transaction processing flow.</span></span>
