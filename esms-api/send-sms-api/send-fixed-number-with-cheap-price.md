# Send fixed number with cheap price

This endpoint is used to send the individually message to the recipient using the fixed number.

It is ideal to send the OTP (One-Time-Password) for use-case like verficiation for example.

## HTTP request

\
<mark style="color:yellow;">**`POST`**</mark> [https://rest.esms.vn/MainService.svc/json/SendMultipleMessage\_V4\_post\_json/](http://rest.esms.vn/MainService.svc/json/SendMultipleMessage_V4_post_json/)\


* **Content Type:** <mark style="color:orange;">application/json</mark>
* **Response Type:** <mark style="color:orange;">application/json</mark>

```json
curl --location 'https://rest.esms.vn/MainService.svc/json/SendMultipleMessage_V4_post_json/' \
--header 'Content-Type: application/json' \
--data '{
   "ApiKey": "{{ApiKey}}",
   "Content": "{{Content}}",
   "Phone": "{{Phone}}",
   "SecretKey": "{{SecretKey}}",
   "SmsType": "8",
   "IsUnicode": "{{IsUnicode}}",
   "Sandbox": "{{Sandbox}}",
   "campaignid": "{{campaignid}}",
   "RequestId": "{{RequestId}}",
   "CallbackUrl": "{{CallbackUrl}}",
   "SendDate":"{{SendDate}}"
}'
```

* **Request body**

<table><thead><tr><th width="145">Paramter</th><th width="121">Type</th><th width="147" data-type="checkbox">Required</th><th>Description</th></tr></thead><tbody><tr><td>ApiKey</td><td>string</td><td>true</td><td>Your API Key.</td></tr><tr><td>Content</td><td>string</td><td>true</td><td>The message content.</td></tr><tr><td>Phone</td><td>string</td><td>true</td><td>The phone number of receivers.</td></tr><tr><td>SecretKey</td><td>string</td><td>true</td><td>Your Secret Key.</td></tr><tr><td>SmsType</td><td>string</td><td>true</td><td>Message type<br>8: Fixed number</td></tr><tr><td>Unicode</td><td>string</td><td>false</td><td><p>Message charset value (<strong>default is 0</strong>):<br>1: Unicode.</p><p>0: Non-Unicode.</p></td></tr><tr><td>Sandbox</td><td>string</td><td>false</td><td>Sandbox option value (<strong>default is 0</strong>):<br>1: For testing purpose to verify the validation of the request. Message is not charged and sent to the receiver.<br>0: Message will be processed to the receiver properly.</td></tr><tr><td>campaignid</td><td>string</td><td>false</td><td>The campaign name of the request.</td></tr><tr><td>RequestId</td><td>string</td><td>false</td><td>The identification value for the request to prevent the the request from duplicated.</td></tr><tr><td>CallbackUrl</td><td>string</td><td>false</td><td>The webhook URL that will receive the status of message after it processed to the operator. It is used for determine whether the SMS is succcessfully delivered to the receiver or failed.<br>See the sample request at <a href="https://samplefordevelopers.esms.vn/#20f85e1f-3d9e-4ff4-bc4f-8d9c9edbc88a">here</a>.<br>More detail at <a href="../callback-url.md">here</a>.</td></tr><tr><td>SendDate</td><td>string</td><td>false</td><td>Scheduler the message to the receiver.<br>If it's empty, the message will be instantly sent to the receiver.<br>Format: <strong>yyyy-mm-dd hh:MM:ss</strong></td></tr></tbody></table>

***

* **Response:**

{% tabs %}
{% tab title="100" %}
```json
{
    "CodeResult": "100",
    "CountRegenerate": 0,
    "SMSID": "d8e0f1f0702544b2acb456ca9ccfd111250"
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

{% tab title="99" %}
```
{
  "error": "Invalid request"
}
```

Connection is error. Contact the admin for reference.
{% endtab %}
{% endtabs %}

* **Response body**

| Parameter    | Type   | Description                                  |
| ------------ | ------ | -------------------------------------------- |
| CodeResult   | string | Response code.                               |
| SMSID        | string | The message id eSMS system.                  |
| ErrorMessage | string | The error message if the request is invalid. |

* _<mark style="color:yellow;">**The detail of error code can refer at**</mark>_ [**Table of error codes**](../table-of-error-codes.md) **.**
* _<mark style="color:yellow;">**Get the  sample of code for programing languagues to use in Postman refer at**</mark>_ [**Link  of code samples**](https://samplefordevelopers.esms.vn/#850974b9-12cf-46f5-946c-e8e15aa3585b)**.**
