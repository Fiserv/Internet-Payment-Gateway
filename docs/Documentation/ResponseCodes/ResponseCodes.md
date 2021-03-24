---
title: Response Codes
author: anna.kopylowicz@firstdata.de
---

###<img alt="Result Code" data-entity-type="file" data-entity-uuid="db9127dc-38a6-46f3-93ad-f7108684b784" src="resultcode.png" /> 

### &nbsp;

### <span lang="EN-US">Address Verification Service (AVS) Results</span>

<span lang="EN-US">The AVS response logic is the following:</span>

  * <span lang="EN-US"><span lang="EN-US"><span lang="EN-US">the&nbsp;</span></span></span>1st letter of the AVS code relates to the street address
  * the 2nd letter of the AVS code relates to the postcode/zip

whereas the letters indicate:

<table>
  <tbody>
    <tr>
      <td>
        <strong>Value</strong>
      </td>
      
      <td>
        &nbsp;&nbsp;
      </td>
      
      <td>
        <strong>Meaning</strong>
      </td>
    </tr>
    
    <tr>
      <td>
        Y
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        <span lang="EN-US">The submitted value matches with the card issuer's records</span>
      </td>
    </tr>
    
    <tr>
      <td>
        N
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        <span lang="EN-US">The submitted value does not match with the card issuer's records</span>
      </td>
    </tr>
    
    <tr>
      <td>
        P
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        <span lang="EN-US">No value has been provided or the provided value has not been checked by the card issuer</span>
      </td>
    </tr>
  </tbody>
</table>

### &nbsp;

### <span lang="EN-US"><span lang="EN-US"><span lang="EN-US">Card Security Code Verification Results</span></span></span>

<table>
  <tbody>
    <tr>
      <td>
        <strong>Value</strong>
      </td>
      
      <td>
        &nbsp;&nbsp;
      </td>
      
      <td>
        <strong>Meaning</strong>
      </td>
    </tr>
    
    <tr>
      <td>
        M
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        Card Security Code matches
      </td>
    </tr>
    
    <tr>
      <td>
        N
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        Card Security Code does not match
      </td>
    </tr>
    
    <tr>
      <td>
        P
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        Not processed
      </td>
    </tr>
    
    <tr>
      <td>
        S
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        Merchant has indicated that the card security code is not present on the card
      </td>
    </tr>
    
    <tr>
      <td>
        U
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        Issuer is not certified and/or has not provided encryption keys
      </td>
    </tr>
    
    <tr>
      <td>
        X
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        No response from the credit card association was received.
      </td>
    </tr>
    
    <tr>
      <td>
        &nbsp;
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        A blank response indicates that no code was sent and that there was no indication that the code was not present on the card.
      </td>
    </tr>
  </tbody>
</table>

### &nbsp;

### Most Common Card Processing Response Codes

<table>
  <tbody>
    <tr>
      <td>
        <p>
          <span><span><span><span><strong><span><span><span>Authorization Response Code</span></span></span></strong></span></span></span></span>
        </p>
      </td>
      
      <td>
        <p>
          &nbsp;
        </p>
        
        <p>
          <span><span><span><span><strong><span><span><span><span>Response Code Description</span></span></span></span></strong></span></span></span></span>
        </p>
      </td>
      
      <td>
        <p>
          &nbsp;
        </p>
        
        <p>
          <span><span><span><span><strong><span><span><span>Gateway Approval Code Example</span></span></span></strong></span></span></span></span>
        </p>
      </td>
    </tr>
    
    <tr>
      <td>
        <p>
          <span><span><span><span><span><span><span>00</span></span></span></span></span></span></span>
        </p>
      </td>
      
      <td>
        <p>
          <span><span><span><span><span><span><span>Transaction has been approved.</span></span></span></span></span></span></span>
        </p>
      </td>
      
      <td>
        <p>
          <span><span><span><span><span><span><span><span>Y:000000:3989951798:PPX:259280509</span></span></span></span></span></span></span></span>
        </p>
      </td>
    </tr>
    
    <tr>
      <td>
        <p>
          <span><span><span><span><span><span><span>05</span></span></span></span></span></span></span>
        </p>
      </td>
      
      <td>
        <p>
          <span><span><span><span><span><span><span>The card being used for the transaction has been rejected by the issuer.</span></span></span></span></span></span></span>
        </p>
      </td>
      
      <td>
        <p>
          <span><span><span><span><span><span><span><span>N:05:Do Not Honour</span></span></span></span></span></span></span></span>
        </p>
      </td>
    </tr>
    
    <tr>
      <td>
        <p>
          <span><span><span><span><span><span><span>-5993</span></span></span></span></span></span></span>
        </p>
      </td>
      
      <td>
        <p>
          <span><span><span><span><span><span><span>The transaction has been cancelled by the consumer. </span></span></span></span></span></span></span>
        </p>
      </td>
      
      <td>
        <p>
          <span><span><span><span><span><span><span>N:-5993:Cancelled by user</span></span></span></span></span></span></span>
        </p>
      </td>
    </tr>
  </tbody>
</table>

### &nbsp;

### Response Codes Related to Configuration Issues

<table>
  <tbody>
    <tr>
      <td>
        <p>
          <span><span><span><span><strong><span><span><span>Authorization Response Code</span></span></span></strong></span></span></span></span>
        </p>
      </td>
      
      <td>
        <p>
          <span><span><span><span><strong><span><span><span><span>Response Code Description</span></span></span></span></strong></span></span></span></span>
        </p>
      </td>
      
      <td>
        <p>
          <span><span><span><span><strong><span><span><span>Gateway Approval Code</span></span></span></strong></span></span></span></span>
        </p>
      </td>
    </tr>
    
    <tr>
      <td>
        <p>
          <span><span><span><span><span><span><span>-5002</span></span></span></span></span></span></span>
        </p>
      </td>
      
      <td>
        <p>
          <span><span><span><span><span><span><span>The merchant does not have a service entry for the card brand that has been used in the transaction request.</span></span></span></span></span></span></span>
        </p>
      </td>
      
      <td>
        <p>
          <span><span><span><span><span><span><span>N:-5002:brand not supported</span></span></span></span></span></span></span>
        </p>
      </td>
    </tr>
    
    <tr>
      <td>
        <span><span><span><span><span><span><span>-12000</span></span></span></span></span></span></span>
      </td>
      
      <td>
        <span><span><span><span><span><span><span>The merchant has the service entry Card Code Mandatory, but sent a MOTO/ECI transaction without card code value. </span></span></span></span></span></span></span>
      </td>
      
      <td>
        <span><span><span><span><span><span><span>N:-12000:Card security code is mandatory</span></span></span></span></span></span></span>
      </td>
    </tr>
    
    <tr>
      <td>
        <p>
          <span><span><span><span><span><span><span>-30053</span></span></span></span></span></span></span>
        </p>
      </td>
      
      <td>
        <p>
          <span><span><span><span><span><span><span>The transaction timed out.</span></span></span></span></span></span></span>
        </p>
      </td>
      
      <td>
        <p>
          &nbsp;
        </p>
        
        <p>
          <span><span><span><span><span><span><span>N:-30053:Communication Error</span></span></span></span></span></span></span>
        </p>
        
        <p>
          &nbsp;
        </p>
      </td>
    </tr>
    
    <tr>
      <td>
        <p>
          <span><span><span><span><span><span><span>-30053</span></span></span></span></span></span></span>
        </p>
      </td>
      
      <td>
        <p>
          <span><span><span><span><span><span><span>Exception occurred retrieving the message from the endpoint.</span></span></span></span></span></span></span>
        </p>
      </td>
      
      <td>
        <p>
          <span><span><span><span><span><span><span>N:-30053:Communication Error</span></span></span></span></span></span></span>
        </p>
      </td>
    </tr>
    
    <tr>
      <td>
        <p>
          <span><span><span><span><span><span><span>-30060</span></span></span></span></span></span></span>
        </p>
      </td>
      
      <td>
        <p>
          <span><span><span><span><span><span><span>An error occured building, parsing or interpreting the message.</span></span></span></span></span></span></span>
        </p>
      </td>
      
      <td>
        <p>
          <span><span><span><span><span><span><span>N:30060:Internal Error</span></span></span></span></span></span></span>
        </p>
      </td>
    </tr>
    
    <tr>
      <td>
        <p>
          <span><span><span><span><span><span><span>-50653</span></span></span></span></span></span></span>
        </p>
      </td>
      
      <td>
        <p>
          <span><span><span><span><span><span><span>Incorrect currency has been sent in the request.</span></span></span></span></span></span></span>
        </p>
      </td>
      
      <td>
        <p>
          <span><span><span><span><span><span><span>N:-50653:Sent invalid currency or no currencies were setup for this store</span></span></span></span></span></span></span>
        </p>
      </td>
    </tr>
  </tbody>
</table>

&nbsp;

### Response Codes Related to First Data Local Payments

<table>
  <tbody>
    <tr>
      <td>
        <p>
          <span><span><span><span><strong><span><span><span>Authorization Response Code</span></span></span></strong></span></span></span></span>
        </p>
      </td>
      
      <td>
        <p>
          <span><span><span><span><strong><span><span><span>Response Code Description</span></span></span></strong></span></span></span></span>
        </p>
      </td>
      
      <td>
        <p>
          <span><span><span><span><strong><span><span><span>Gateway Approval Code</span></span></span></strong></span></span></span></span>
        </p>
      </td>
    </tr>
    
    <tr>
      <td>
        <p>
          <span><span><span><span><span><span><span>-PP00001</span></span></span></span></span></span></span>
        </p>
      </td>
      
      <td>
        <p>
          <span><span><span><span><span><span><span>Cardholder did not return from local payment redirection.</span></span></span></span></span></span></span>
        </p>
      </td>
      
      <td>
        <p>
          <span><span><span><span><span><span><span>N:-PP00001:Cardholder did not return from alternate payment</span></span></span></span></span></span></span>
        </p>
      </td>
    </tr>
    
    <tr>
      <td>
        <p>
          <span><span><span><span><span><span><span>INPUT_DATA</span></span></span></span></span></span></span>
        </p>
      </td>
      
      <td>
        <p>
          <span><span><span><span><span><span><span>Transaction input data are incorrect, channel tag or transaction has not been found.</span></span></span></span></span></span></span>
        </p>
      </td>
      
      <td>
        <p>
          <span><span><span><span><span><span><span>N:INPUT_DATA:Invalid input data</span></span></span></span></span></span></span>
        </p>
      </td>
    </tr>
    
    <tr>
      <td>
        <p>
          <span><span><span><span><span><span><span>QUOTA</span></span></span></span></span></span></span>
        </p>
      </td>
      
      <td>
        <p>
          <span><span><span><span><span><span><span>Refund quota exceeded - not enough funds available.</span></span></span></span></span></span></span>
        </p>
      </td>
      
      <td>
        <p>
          <span><span><span><span><span><span><span>N:QUOTA:APM</span></span></span></span></span></span></span>
        </p>
      </td>
    </tr>
  </tbody>
</table>

&nbsp;

### &nbsp;

&nbsp;

### &nbsp;
