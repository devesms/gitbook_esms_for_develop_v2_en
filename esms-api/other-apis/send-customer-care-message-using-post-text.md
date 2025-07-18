---
description: >-
  API dùng để gửi tin Quảng cáo đến khách hàng. Mỗi request tối thiểu 30 số để
  được duyệt tin và tối đa 5000 số.
---

# Send customer care message using POST TEXT

## HTTP request

\
<mark style="color:yellow;">**`POST`**</mark> [https://rest.esms.vn/MainService.svc/json/SendMultipleSMSBrandname](http://rest.esms.vn/MainService.svc/json/SendMultipleSMSBrandname)

* **Content Type:** <mark style="color:orange;">application/text/plain</mark>
* **Response Type:** <mark style="color:orange;">application/json</mark>

```
curl --location 'https://rest.esms.vn/MainService.svc/json/SendMultipleMessage_V4/' \
--header 'Content-Type: text/plain' \
--data '<RQST>
<APIKEY><{{ApiKey}}</APIKEY>
<SECRETKEY>{{SecretKey}}</SECRETKEY>
<CONTENT>{{Content}}</CONTENT>
<SMSTYPE>2</SMSTYPE>
<BRANDNAME>{{Brandname}}</BRANDNAME>
<REQUESTID>{{RequestId}}</REQUESTID>
<SENDDATE>{{senddate}}</SENDDATE>
<CALLBACKURL>{{callbackUrl}}}</CALLBACKURL>
<CONTACTS>
<CUSTOMER><PHONE>{{Phone}}</PHONE></CUSTOMER>
</CONTACTS>
</RQST>'
```

* **Request body**

<table><thead><tr><th width="167">Paramter</th><th width="149">Type</th><th width="141" data-type="checkbox">Required</th><th>Description</th></tr></thead><tbody><tr><td>APIKEY</td><td>string</td><td>true</td><td>Your API Key.</td></tr><tr><td>SECRETKEY</td><td>string</td><td>true</td><td>Your Secret Key.</td></tr><tr><td>CONTENT</td><td>string</td><td>true</td><td>The content of SMS.</td></tr><tr><td>SMSTYPE</td><td>string</td><td>true</td><td>Type of SMS<br>1: Advertising.</td></tr><tr><td>BRANDNAME</td><td>string</td><td>true</td><td>The name of the sender is shown in the header of the customer's message. Pre-registration is required.</td></tr><tr><td>REQUESTID</td><td>string</td><td>false</td><td>Partner ID passed to block duplicates and check if needed.<br>Maximum length 50 characters.<br>Each RequestId passed is valid for blocking for 24 hours.</td></tr><tr><td>PHONE</td><td>string</td><td>true</td><td>The phone number of receiver.</td></tr><tr><td>SENDDATE</td><td>string</td><td>false</td><td>Scheduler the message to the receiver.<br>If it's empty, the message will be instantly sent to the receiver.<br>Format: <strong>yyyy-mm-dd hh:MM:ss</strong></td></tr><tr><td>CALLBACKURL</td><td>string</td><td>false</td><td>The webhook URL that will receive the status of message after it processed to the operator. It is used for determine whether the SMS is succcessfully delivered to the receiver or failed.<br>See the sample request at <a href="https://samplefordevelopers.esms.vn/#20f85e1f-3d9e-4ff4-bc4f-8d9c9edbc88a">here</a>.<br>More detail at <a href="../callback-url.md">here</a>.</td></tr></tbody></table>

***

* **Response:**

{% tabs %}
{% tab title="100" %}
```json
{
    "CodeResult": "100",
    "CountRegenerate": 0,
    "SMSID": "d533459ee42b2b9525ba9eabf6a8156"
}
```

**Valid request.**
{% endtab %}

{% tab title="101" %}
```json
{
    "CodeResult": "101",
    "CountRegenerate": 0,
    "ErrorMessage": "Authorize Failed"
}
```

**Invalid credential.**
{% endtab %}

{% tab title="104" %}
```json
{
    "CodeResult": "104",
    "CountRegenerate": 0,
    "ErrorMessage": "Brand name code is not exist"
}
```

**Invalid brandname.**
{% endtab %}

{% tab title="107" %}
```
{
    "CodeResult": "107",
    "CountRegenerate": 0,
    "ErrorMessage": "Each request has at least 30 numbers to be approved"
}
```

Receivers are not enough.
{% endtab %}

{% tab title="124" %}
```
{
    "CodeResult": "124",
    "CountRegenerate": 0,
    "ErrorMessage": "Request exist 1"
}
```

**Trùng RequestId. Mỗi RequestId chỉ được gửi cho 1 request.**
{% endtab %}
{% endtabs %}

* **Response body:**

| Parameter    | Type   | Description                                  |
| ------------ | ------ | -------------------------------------------- |
| CodeResult   | string | Response code.                               |
| SMSID        | string | The message id eSMS system.                  |
| ErrorMessage | string | The error message if the request is invalid. |

* _<mark style="color:yellow;">**The detail of error code can refer at**</mark>_ [**Table of error codes**](../table-of-error-codes.md) **.**
* _<mark style="color:yellow;">**Get the  sample of code for programing languagues to use in Postman refer at**</mark>_ [**Link  of code samples**](https://samplefordevelopers.esms.vn/#850974b9-12cf-46f5-946c-e8e15aa3585b)**.**
