# Send fixed number using GET

## HTTP request

\
<mark style="color:green;">**`GET`**</mark> <mark style="color:blue;">https://rest.esms.vn/MainService.svc/json/SendMultipleMessage\_V4\_get?Phone=\{{Phone\}}\&Content=\{{Content\}}\&ApiKey=\{{ApiKey\}}\&SecretKey=\{{SecretKey\}}\&IsUnicode=\{{IsUnicode\}}\&SmsType=8\&CallbackUrl=\{{CallbackUrl\}}\&RequestId=\{{RequestId\}}\&SendDate=\{{yyyy-mm-dd HH:mm:hh\}}</mark>

* **Response Type:** <mark style="color:orange;">application/json</mark>

```json
curl --location -g 'https://rest.esms.vn/MainService.svc/json/SendMultipleMessage_V4_get?Phone={{Phone}}&Content={{Content}}&ApiKey={{ApiKey}}&SecretKey={{SecretKey}}&IsUnicode={{IsUnicode}}&SmsType=8&CallbackUrl={{CallbackUrl}}&RequestId={{RequestId}}&SendDate={{yyyy-mm-dd%20HH%3Amm%3Ahh}}'
```

* **Request Params:**

<table><thead><tr><th width="148">Parameters</th><th width="139">Type</th><th width="142" data-type="checkbox">Required</th><th>Description</th></tr></thead><tbody><tr><td>Phone</td><td>string</td><td>true</td><td>The phone number of receiver.</td></tr><tr><td>Content</td><td>string</td><td>true</td><td>The content of message.</td></tr><tr><td>ApiKey</td><td>string</td><td>true</td><td>Your API Key.</td></tr><tr><td>SecretKey</td><td>string</td><td>true</td><td>Your Secret Key.</td></tr><tr><td>Unicode</td><td>string</td><td>false</td><td><p>GửMessage charset value (<strong>default is 0</strong>):<br>1: Unicode.</p><p>0: Non-Unicode.</p></td></tr><tr><td>SmsType</td><td>string</td><td>true</td><td>Message type<br>8: Fixed number</td></tr><tr><td>CallbackUrl</td><td>string</td><td>false</td><td>The webhook URL that will receive the status of message after it processed to the operator. It is used for determine whether the SMS is succcessfully delivered to the receiver or failed.<br>See the sample request at <a href="https://samplefordevelopers.esms.vn/#20f85e1f-3d9e-4ff4-bc4f-8d9c9edbc88a">here</a>.<br>More detail at <a href="../callback-url.md">here</a>.</td></tr><tr><td>RequestId</td><td>string</td><td>false</td><td>Partner ID passed to block duplicates and check if needed.<br>Maximum length 50 characters.<br>Each RequestId passed is valid for blocking for 24 hours.</td></tr><tr><td>SendDate</td><td>string</td><td>false</td><td>Scheduler the message to the receiver.<br>If it's empty, the message will be instantly sent to the receiver.<br>Format: <strong>yyyy-mm-dd hh:MM:ss</strong></td></tr></tbody></table>

***

* **Response:**

{% tabs %}
{% tab title="100" %}
```
{
    "CodeResult": "100",
    "CountRegenerate": 0,
    "SMSID": "d8e0f1f0702544b2acb456ca9ccfd111250"
}
```

**Valid request.**
{% endtab %}

{% tab title="101" %}
```
{
    "CodeResult": "101",
    "CountRegenerate": 0,
    "ErrorMessage": "Authorize Failed"
}
```

**Invalid credential.**
{% endtab %}

{% tab title="99" %}
```json
{
  "error": "Invalid request"
}
```

Connection is error. Contact the admin for reference.
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
