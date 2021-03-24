---
title: Billing/Shipping Information 
author: steffen.dangel@firstdata.de
---

If you post a HTML form to initiate the payment, you can include billing and shipping information in your request by using the following fields. Some of these fields are mandatory for specific alternative payment methods or relevant for fraud prevention purpose.

##### Alternative Options

> [Billing information in API requests][1]  
> [Shipping information in API requests][2]

&nbsp;

### Billing Information

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
        bcompany
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        Customer's company name. Alphanumeric characters, spaces and dashes.
      </td>
    </tr>
    
    <tr>
      <td>
        bname
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        Customer's name. Alphanumeric characters, spaces and dashes.
      </td>
    </tr>
    
    <tr>
      <td>
        baddr1
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        Customer's billing address 1. Limit of 96 characters including spaces.
      </td>
    </tr>
    
    <tr>
      <td>
        baddr2
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        Customer's billing address 2. Limit of 96 characters including spaces.
      </td>
    </tr>
    
    <tr>
      <td>
        bcity
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        Billing City. Limit of 96 characters including spaces.
      </td>
    </tr>
    
    <tr>
      <td>
        bstate
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        State, Province or Territory. Limit of 96 characters including spaces.
      </td>
    </tr>
    
    <tr>
      <td>
        bcountry
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        Country of Billing Address. Two letter country code.
      </td>
    </tr>
    
    <tr>
      <td>
        bzip
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        Zip or Postal Code. Limit of 24 characters including spaces.
      </td>
    </tr>
    
    <tr>
      <td>
        phone
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        Customer's Phone Number. Limit of 32 characters.
      </td>
    </tr>
    
    <tr>
      <td>
        fax
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        Customer's Fax Number. Limit of 32 characters.
      </td>
    </tr>
    
    <tr>
      <td>
        email
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        Customer's Email Address. Limit of 254 characters.
      </td>
    </tr>
  </tbody>
</table>

&nbsp;

### Shipping Information

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
    
    <tr>
      <td>
        sname
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        Ship-to name. Alphanumeric characters, spaces and dashes.
      </td>
    </tr>
    
    <tr>
      <td>
        saddr1
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        Shipping Address Line 1. Limit of 96 characters including spaces.
      </td>
    </tr>
    
    <tr>
      <td>
        saddr2
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        Shipping Address Line 2. Limit of 96 characters including spaces.
      </td>
    </tr>
    
    <tr>
      <td>
        scity
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        Shipping City. Limit of 96 characters including spaces.
      </td>
    </tr>
    
    <tr>
      <td>
        sstate
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        State, Province or Territory. Limit of 96 characters including spaces.
      </td>
    </tr>
    
    <tr>
      <td>
        scountry
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        Country of Billing Address. Two letter country code.
      </td>
    </tr>
    
    <tr>
      <td>
        szip
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        Zip or Postal Code. Limit of 24 characters including spaces.
      </td>
    </tr>
  </thead>
</table>

 [1]: http://test-ndpfdc.pantheonsite.io/org/gateway/docs/api#billing
 [2]: http://test-ndpfdc.pantheonsite.io/org/gateway/docs/api#shipping
