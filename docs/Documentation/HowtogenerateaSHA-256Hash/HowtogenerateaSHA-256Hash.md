---
title: How to generate a SHA-256 Hash
author: adriana.vas@firstdata.de
---

If you are using a HTML form to initiate the _sale_ or _preauth_ transaction, your request needs to include a security hash in order to allow us to verify the message integrity.

There are two options for you to chose from - a simple version with only five transaction parameters (parameter _hash_) or a hash that includes all request parameters in ascending order of the parameter names (parameter _hashExtended_).

### Creating the simple version (_hash_)  
&nbsp;

  * storename = 98765432101
  * txndatetime = 2013:07:16-09:57:08
  * chargetotal = 1.00
  * currency = 826
  * sharedsecret = TopSecret  
    &nbsp;

**Step 1** - Collect selected parameters: storename, txndatetime, chargetotal, currency and sharedsecret and join the parameters’ values to one string (use only parameters’ values and not the parameters’ names).

<pre>987654321012013:07:16-09:57:081.00826TopSecret</pre>

**Step 2** - Convert the created string to its ascii hexadecimal representation.

<pre>3938373635343332313031323031333a30373a31362d30393a35373a3038312e3030383236546f70536563726574</pre>

**Step 3** - Pass the ascii hexadecimal representation of the created string to the SHA-256 algorithm.

<pre>SHA256(3938373635343332313031323031333a30373a31362d30393a35373a3038312e3030383236546f70536563726574)</pre>

**Step 4** - Use the value returned by the SHA-256 algorithm and submit it to our payment gateway in the given form.

<pre>3d7e75aa0b4e0e1d4a7ac87e451e64692cced46f4358ef35a69d96721341243c</pre>

<pre>&lt;input type="hidden" name="hash"
value="3d7e75aa0b4e0e1d4a7ac87e451e64692cced46f4358ef35a69d96721341243c"/&gt;</pre>

### &nbsp;

### Creating the hash with all parameters (_hashExtended_)  
&nbsp;

  * P1 = abc
  * P2 = xyz
  * P3 = ccc
  * sharedsecret = TopSecret
  * t1=zzz
  * t2=yyy  
    &nbsp;

**Step 1**&nbsp; - Extended hash needs to be calculated using all request parameters in ascending order of the parameter names, adding sharedsecret at last. Join the parameters’ values to one string (use only parameters’ values and not the parameters’ names).

<pre>abcxyzccczzzyyyTopSecret</pre>

  
**Step 2** - Convert the created string to its ascii hexadecimal representation.

<pre>3938373635343332313031323031333a30373a31362d30393a35373a3038312e3030383236546f70536563726574</pre>

**Step 3** - Pass the ascii hexadecimal representation of the created string to the SHA-256 algorithm.

<pre>SHA256(3938373635343332313031323031333a30373a31362d30393a35373a3038312e3030383236546f70536563726574)</pre>

**Step 4** - Use the value returned by the SHA-256 algorithm and submit it to our payment gateway in the given form.

<pre>3d7e75aa0b4e0e1d4a7ac87e451e64692cced46f4358ef35a69d96721341243c</pre>

<pre>&lt;input type="hidden" name="hashExtended"
value="3d7e75aa0b4e0e1d4a7ac87e451e64692cced46f4358ef35a69d96721341243c"/&gt;</pre>

&nbsp;
