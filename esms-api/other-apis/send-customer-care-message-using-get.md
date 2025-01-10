# Send customer care message using GET

## HTTP request

\
<mark style="color:green;">**`GET`**</mark> <mark style="color:blue;">https://rest.esms.vn/MainService.svc/json/SendMultipleMessage\_V4\_get?Phone=\{{Phone\}}\&Content=\{{Content\}}\&ApiKey=\{{ApiKey\}}\&SecretKey=\{{SecretKey\}}\&IsUnicode=\{{IsUnicode\}}\&Brandname=\{{Brandname\}}\&SmsType=2\&CallbackUrl=\{{CallbackUrl\}}\&RequestId=\{{RequestId\}}\&SendDate=\{{yyyy-mm-dd HH:mm:hh\}}\&SandBox=\{{SandBox\}}</mark>

* **Response Type:** <mark style="color:orange;">application/json</mark>

```
curl --location -g 'https://rest.esms.vn/MainService.svc/json/SendMultipleMessage_V4_get?Phone={{Phone}}&Content={{Content}}&ApiKey={{ApiKey}}&SecretKey={{SecretKey}}&IsUnicode={{IsUnicode}}&Brandname={{Brandname}}&SmsType=2&CallbackUrl={{CallbackUrl}}&RequestId={{RequestId}}&SendDate={{yyyy-mm-dd%20HH%3Amm%3Ahh}}'
```

* **Request Params:**

<table><thead><tr><th width="148">Parameter</th><th width="136">Type</th><th width="134" data-type="checkbox">Required</th><th>Description</th></tr></thead><tbody><tr><td>ApiKey</td><td>string</td><td>true</td><td>Your API Key.</td></tr><tr><td>Content</td><td>string</td><td>true</td><td>The content of message.</td></tr><tr><td>Phone</td><td>string</td><td>true</td><td>The phone number of receiver.</td></tr><tr><td>SecretKey</td><td>string</td><td>true</td><td>Your Secret Key.</td></tr><tr><td>Brandname</td><td>string</td><td>true</td><td>The name of the sender is shown in the header of the customer's message. Pre-registration is required.</td></tr><tr><td>SmsType</td><td>string</td><td>true</td><td>Message type:<br>2: Customer care message.</td></tr><tr><td>IsUnicode</td><td>string</td><td>false</td><td><p>Message charset value (<strong>default is 0</strong>):<br>1: Unicode.</p><p>0: Non-Unicode.</p></td></tr><tr><td>Sandbox</td><td>string</td><td>false</td><td>Sandbox option value (<strong>default is 0</strong>):<br>1: For testing purpose to verify the validation of the request. Message is not charged and sent to the receiver.<br>0: Message will be processed to the receiver properly.</td></tr><tr><td>RequestId</td><td>string</td><td>false</td><td>The identification value for the request to prevent the the request from duplicated.</td></tr><tr><td>SendDate</td><td>string</td><td>false</td><td>Scheduler the message to the receiver.<br>If it's empty, the message will be instantly sent to the receiver.<br>Format: <strong>yyyy-mm-dd hh:MM:ss</strong></td></tr><tr><td>campaignid</td><td>string</td><td>false</td><td>The campaign name of the request.</td></tr><tr><td>CallbackUrl</td><td>string</td><td>false</td><td>The webhook URL that will receive the status of message after it processed to the operator. It is used for determine whether the SMS is succcessfully delivered to the receiver or failed.<br>See the sample request at <a href="https://samplefordevelopers.esms.vn/#20f85e1f-3d9e-4ff4-bc4f-8d9c9edbc88a">here</a>.<br>More detail at <a href="../callback-url.md">here</a>.</td></tr></tbody></table>



***

* **Response:**

{% tabs %}
{% tab title="100" %}
```json
{
    "CodeResult": "100",
    "CountRegenerate": 0,
    "SMSID": "ebe101db-87cd-4285-b97b-6a7a90455ded30"
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

{% tab title="124" %}
```json
{
    "CodeResult": "124",
    "CountRegenerate": 0,
    "ErrorMessage": "Request exist 1"
}
```

**Duplicate request.**
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
