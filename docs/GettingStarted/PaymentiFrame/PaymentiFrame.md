---
title: Payment iFrame
author: steffen.dangel@firstdata.de
---

If you want to control the screen design of your checkout pages but at the same time avoid handling sensitive payment information such as credit card numbers, you can use a hosted form for the required input fields and insert that form in an iFrame on your website. The data that your customer enters to that form will be directly sent to our Gateway.

&nbsp;

### Required Fields

In addition to the [fields that are mandatory for every payment request][1] that you initiate through a HTML form, the following fields are required for the iFrame integration:

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
        checkoutoption
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        For the iFrame integration, set the value for this parameter to <em>simpleform</em>&nbsp;<em> </em>
      </td>
    </tr>
    
    <tr>
      <td>
        hostURI
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        <p>
          Provide the URI where the Gateway can send back the message with Windows.postMessage() API available in HTML 5 enabled browsers, e.g.https://www.yoursite.com/checkout
        </p>
      </td>
    </tr>
  </tbody>
</table>

### &nbsp;

### Optional Fields

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
        hexColorCode
      </td>
      
      <td>
        &nbsp;
      </td>
      
      <td>
        <p>
          This field allows you to customize the colors of buttons within the iFrame. If you e.g. send the value<em> #9c22ce</em>, the color of buttons will be violet.
        </p>
      </td>
    </tr>
  </tbody>
</table>

### &nbsp;

### iFrame Size Requirements

  * Minimum height 900px
  * Minimum width 406px

### &nbsp;

### <span><span><span><span><span>JSP Example</span></span></span></span></span>

<pre><span><span><span><span><span>&lt;div id="embeddableConnect"&gt;</span></span></span></span></span> 
<span><span><span><span><span>&lt;table border="0" cellpadding="0" cellspacing="0" width="100%"&gt;</span></span></span></span></span> 
<span><span><span><span><span>&lt;tbody&gt;</span></span></span></span></span> 
<span><span><span><span><span>&lt;tr&gt;</span></span></span></span></span> 
<span><span>&lt;iframe name="myFrame" id="myFrame" src="#" width="460px" height="900px" style="border: none;"&gt;</span></span>
<span><span><span><span><span>Your browser does not support inline frames.</span></span></span></span></span> 
<span><span><span><span><span>&lt;/iframe&gt;</span></span></span></span></span> 
<span><span><span><span><span>&lt;/tr&gt;</span></span></span></span></span> 
<span><span><span><span><span>&lt;/tbody&gt;</span></span></span></span></span> 
<span><span><span><span><span>&lt;/table&gt;</span></span></span></span></span> 
<span><span><span><span><span>&lt;/div&gt;</span></span></span></span></span> 
</pre>

&nbsp;

### <span><span><span><span><span>JavaScript Changes</span></span></span></span></span>

<span><span><span><span><span>You need to register a method e.g. 'receiveMessage' with the listener like</span></span></span></span></span>

<pre><span><span><span><span><span>window.addEventListener("message", receiveMessage, false);</span></span></span></span></span>
<span><span><span><span><span>function receiveMessage(event){</span></span></span></span></span>
<span><span><span>if (event.origin != "https://test.ipg-online.com")// Need to replace this URI with production one;</span></span></span>
<span><span><span>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; var connectForm = event.source.document.forms[0]; </span></span></span>
<span><span><span>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; var newForm = document.createElement("form");</span></span></span>
<span><span><span><span><span>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; newForm.setAttribute('method',"post");</span></span></span></span></span>
<span><span><span><span><span>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; newForm.setAttribute('action',event.data);</span></span></span></span></span>
<span><span><span><span><span>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; newForm.setAttribute('id',"newForm");</span></span></span></span></span>
<span><span><span><span><span>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; newForm.setAttribute('name',"newForm");</span></span></span></span></span>
<span><span><span><span><span>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; document.body.appendChild(newForm);</span></span></span></span></span>
<span><span><span><span><span>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; for(j=0 ; j&lt;connectForm.elements.length; j++){</span></span></span></span></span>
<span><span><span><span><span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;var element = connectForm.elements[j];</span></span></span></span></span>
<span><span><span><span><span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;var input = document.createElement("input");</span></span></span></span></span>
<span><span><span><span><span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;input.setAttribute("type", "hidden");</span></span></span></span></span>
<span><span><span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;input.setAttribute("name", element.name);</span></span></span>
<span><span><span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;input.setAttribute("value", element.value);</span></span></span>
<span><span><span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;document.newForm.appendChild(input);</span></span></span>
<span><span><span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; }</span></span></span>
<span><span><span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;document.newForm.submit();</span></span></span>
<span><span><span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; }&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;</span></span></span>
</pre>

&nbsp;

 [1]: http://test-ndpfdc.pantheonsite.io/org/gateway/node/90
