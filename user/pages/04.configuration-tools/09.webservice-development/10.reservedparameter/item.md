---
title: 'Webservice format and reserved parameter'
---

Webservice format and reserved parameter
----------------------------------------

The web service API returns responses in JSON format. This format can be
changed on a per-call basis. To accomplish this we would need to
implement the code to support the desired format [like this code which
implements the JSON
format](https://github.com/tsolucio/corebos/blob/master/include/Webservices/OperationManagerEnDecode.php),
add the new format to [the array of supported
formats](https://github.com/tsolucio/corebos/blob/master/include/Webservices/OperationManager.php#L13)
and then indicate the format using the special reserved parameter
**format** in the GET/POST call.

&lt;WRAP center round important 80%&gt; Note that this implies that NO
web service end point may use a parameter named **format** as this
parameter is used for this sole purpose. &lt;/WRAP&gt;
