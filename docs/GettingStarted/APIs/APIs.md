
### APIs
---

For server-to-server interactions with the First Data Gateway, we provide APIs that give you&nbsp;<span><span><span><span><span><span><span><span>maximum </span></span></span></span><span><span><span><span>flexibility in implementing custom business logic and full control over the look and feel of the customer journey.</span></span></span></span></span></span></span></span>

<span><span><span><span><span><span><span><span>This type of integration suits best f</span></span></span></span></span></span></span></span>or&nbsp;steps where no direct consumer interaction is required and no sensitive cardholder data is getting processed.

Please note that if you store or process cardholder data within your own application, you must ensure that your system components are compliant with the Data Security Standard of the Payment Card Industry (PCI DSS). Depending on your transaction volume, an assessment by a Qualified Security Assessor may be mandatory to declare your compliance status.

For tokenization of&nbsp;card details that you can then use for later payment transactions via&nbsp;API requests,&nbsp;please have a look at our [JavaScript option][1] for this purpose.

<img alt="API option" data-align="center" data-entity-type="file" data-entity-uuid="cf386602-83ec-4212-8839-67408ae1f79d" src="/files/API-option.png" /> 

&nbsp;

### API Options

<table>
  <tbody>
    <tr>
      <td>
        <strong>REST API</strong>
      </td>
      
      <td>
        &nbsp;&nbsp;
      </td>
      
      <td>
        Simple lightweight API for the most common operations in <strong>Card Not Present </strong>scenarios. Covers requests and responses for payment transactions, inquiries, payment schedules, payment tokens, card verification and currency conversion.
      </td>
      
      <td>
        &nbsp;&nbsp;
      </td>
      
      <td>
        <a href="https://docs.firstdata.com/org/gateway/docs/api">REST API Reference</a>
      </td>
    </tr>
    
    <tr>
      <td>
        <strong>SOAP API</strong>
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        Language and platform independent API that covers both <strong>Card Not Present and Card Present</strong> scenarios.
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        <a href="https://docs.firstdata.com/org/gateway/node/389">SOAP API Reference</a>
      </td>
    </tr>
    
    <tr>
      <td>
        <strong>Nexo Acquirer Protocol</strong>
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        ISO 20022 based standard interface for <strong>Card Present </strong>scenarios allowing interoperability between different implementations. It handles, amongst other features, the authorization, pre-authorization, refund, cancellation and rejection of card transactions.<br /> <em>Please note that Nexo-based integrations to our gateway require an implementation project where integration details will be mutually agreed.</em>
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        <a href="https://www.nexo-standards.org/user?category=protocols&about=nexo-acquirer-protocol">Nexo Specification</a>
      </td>
    </tr>
  </tbody>
</table>

&nbsp;

##### Alternative Options

> [Hosted Payment Pages][2]  
> [Direct Post][3]

&nbsp;

 [1]: https://docs.firstdata.com/org/gateway/node/1040
 [2]: https://docs.firstdata.com/org/gateway/node/316
 [3]: https://docs.firstdata.com/org/gateway/node/350
