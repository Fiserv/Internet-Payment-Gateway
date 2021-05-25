Billing/Shipping Information 
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
        <pre>
bcompany </pre>
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        Customer's company name. Alphanumeric characters, spaces and dashes limited to 96.
      </td>
    </tr>
    
    <tr>
      <td>
        <pre>
bname</pre>
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        Customer's name. Alphanumeric characters, spaces and dashes limited to 96.
      </td>
    </tr>
    
    <tr>
      <td>
        <pre>
baddr1</pre>
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
        <pre>
baddr2</pre>
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
        <pre>
bcity</pre>
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
        <pre>
bstate</pre>
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
        <pre>
bcountry</pre>
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
        <pre>
bzip</pre>
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
        <pre>
phone</pre>
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
        <pre>
fax</pre>
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
        <pre>
email</pre>
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
        <pre>
sname</pre>
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        Ship-to name. Alphanumeric characters, spaces and dashes limited to 96.
      </td>
    </tr>
    
    <tr>
      <td>
        <pre>
saddr1</pre>
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
        <pre>
saddr2</pre>
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
        <pre>
scity</pre>
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
        <pre>
sstate</pre>
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
        <pre>
scountry</pre>
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
        <pre>
szip</pre>
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

 [1]: http://docs.firstdata.com/org/gateway/docs/api#billing
 [2]: http://docs.firstdata.com/org/gateway/docs/api#shipping
