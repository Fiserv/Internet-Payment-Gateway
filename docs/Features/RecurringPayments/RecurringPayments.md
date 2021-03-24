---
title: Recurring Payments
author: adriana.vas@firstdata.de
---

  
Recurring payments can either be triggered by your system everytime a payment is due or you can make use of our scheduler that allows you to define the frequency and period (e.g. every three days, every second week, every month, once a year, etc.).

&nbsp;

## Triggering Recurring Payments

When triggering Recurring Payments through our [API][1], you need to indicate if the transaction you are sending is the first in series or a subsequent transaction.

&nbsp;

## Using the Scheduler

Recurring Payments that shall be periodically triggered by our Gateway can be installed via three different options:

&nbsp;

#### Option 1:  
Schedule recurring payments using our API

The action RecurringPayment allows you to install, modify or cancel periodic payments in a way that  
subsequent transactions will automatically be triggered by the gateway.

For every recurring transaction, the gateway can send a server-to-server transaction notification to a  
defined Notification URL. Please contact your local support team to get your URL registered for these  
notifications.

&nbsp;

#### Option 2:  
Make payments recurring that get initiated through your website

To use this feature, the following additional parameters will have to be submitted in the transaction request:

<table>
  <tbody>
    <tr>
      <td>
        <p>
          <strong>Field Name</strong>
        </p>
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        <p>
          <strong>Possible Values</strong>
        </p>
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        <p>
          <strong>Description</strong>
        </p>
      </td>
    </tr>
    
    <tr>
      <td>
        <code>recurringInstallmentCount</code>
      </td>
      
      <td>
        &nbsp;&nbsp;
      </td>
      
      <td>
        <p>
          Number between 1 and 999
        </p>
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        <p>
          Number of installments to be made including the initial transaction submitted
        </p>
      </td>
    </tr>
    
    <tr>
      <td>
        <code>recurringInstallmentPeriod</code>
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        <p>
          day
        </p>
        
        <p>
          week
        </p>
        
        <p>
          month
        </p>
        
        <p>
          year
        </p>
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        <p>
          The periodicity of the recurring payment
        </p>
      </td>
    </tr>
    
    <tr>
      <td>
        <code>recurringInstallmentFrequency</code>
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        <p>
          Number between 1 and 99
        </p>
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        <p>
          The time period between installments
        </p>
      </td>
    </tr>
    
    <tr>
      <td>
        <code>recurringComments</code>
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        <p>
          Limit of 100
        </p>
        
        <p>
          characters,
        </p>
        
        <p>
          including
        </p>
        
        <p>
          spaces
        </p>
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        <p>
          Any comments about the recurring transaction
        </p>
      </td>
    </tr>
  </tbody>
</table>

Note that the start date of the recurring payments will be the current date and will be automatically calculated by the system.

&nbsp;

#### Option 3:  
Make payments recurring that you enter via the Virtual Terminal

The Recurring Payments section in the Virtual Terminal allows you to make a credit card (Sale) transaction recurring.

  1. To make a transaction recurring, select the _Yes_ checkbox next to _Make recurring?_  
    &nbsp;
  2. Next enter how often you wish to charge the customer. In the _Bill the customer_ fields, enter a number from 1 to 999 with no decimal point and select day, week, month, or year in the dropdown box. For example, if you wish to charge the customer once a year, enter the number 1 and select _year_ in the dropdown box. To charge the customer twice a year (once every 6 months), you would enter the number 6 and select month in the dropdown box.  
    &nbsp;
  3. Select the month / day / year to start charging the customer in the _Start on_ dropdown boxes.  
    &nbsp;
  4. Enter the number of times to charge the customer in the _End After_ textbox.

&nbsp;

 [1]: http://test-ndpfdc.pantheonsite.io/org/gateway/docs/api
