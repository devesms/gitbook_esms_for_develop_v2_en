# Send message via Zalo

This endpoint is used to send Zalo messages individually (1 request per message).&#x20;

It is ideal to send single personalized messages for use-cases like notifications, alerting or marketing for example.

## HTTP request

\
<mark style="color:yellow;">**`POST`**</mark> [https://rest.esms.vn/MainService.svc/json/SendZaloMessage\_V5\_post/](http://rest.esms.vn/MainService.svc/json/SendZaloMessage_V5_post/)

* **Content Type:** <mark style="color:orange;">application/json</mark>
* **Response Type:** <mark style="color:orange;">application/json</mark>

{% code overflow="wrap" %}
```json
curl --location 'https://rest.esms.vn/MainService.svc/json/SendZaloMessage_V5_post/' \
--header 'Content-Type: application/json' \
--data '{
    "ApiKey": "{{ApiKey}}",
    "SecretKey": "{{SecretKey}}",
    "OAID": "{{OAID}}",
    "Phone": "{{Phone}}",
    "TempData": [
        {
            "key": "{{key1}}",
            "value": "{{value1}}"
        },
        {
            "key": "{{key2}}",
            "value": "{{value2}}"
        }
    ],
    "SendDate": "{{SendDate}}",
    "TempID": "{{TempID}}",
    "campaignid": "{{Campaignid}}",
    "Sandbox": "{{Sandbox}}",
    "CallbackUrl": "{{CallbackUrl}}"
}'
```
{% endcode %}

* **Request body**

<table><thead><tr><th width="152">Parameter</th><th width="128">Type</th><th width="137" data-type="checkbox">Required</th><th>Description</th></tr></thead><tbody><tr><td>Phone</td><td>string</td><td>true</td><td>The phone number of receivers.</td></tr><tr><td>ApiKey</td><td>string</td><td>true</td><td>Your API Key.</td></tr><tr><td>SecretKey</td><td>string</td><td>true</td><td>Your Secret Key.</td></tr><tr><td>OAID</td><td>string</td><td>true</td><td><p>Zalo OA Id is the Zalo Official Account Id of the organization. It can be obtained by accessing to the Zalo administrator page.</p><p><strong>Note: Pre-registration is required.</strong></p></td></tr><tr><td>TempData</td><td>Json object</td><td>true</td><td>The dynamic json object of the template that is registered at Zalo. <br>The template data structure is specified separatedly for each teamplate.</td></tr><tr><td>SendDate</td><td>string</td><td>false</td><td>Schedule the time when the message to the receiver.<br>If it's empty, the message will be instantly sent to the receiver.<br>Format: <strong>yyyy-mm-dd hh:MM:ss</strong></td></tr><tr><td>TempID </td><td>string</td><td>true</td><td>The ID of template for the OA that is registered and provided by eSMS at Zalo to partner.<br>Each template will have a specified structure of body.</td></tr><tr><td>campaignid</td><td>string</td><td>false</td><td>The campaign name of request</td></tr><tr><td>Sandbox</td><td>string</td><td>false</td><td>Sandbox option value (<strong>default is 0</strong>):<br>1: For testing purpose to verify the validation of the request. Message is not charged and sent to the receiver.<br>0: Message will be processed to the receiver properly.</td></tr><tr><td>CallbackUrl</td><td>string</td><td>false</td><td>The webhook URL that will receive the status of message after it processed to the operator. It is used for determine whether the SMS is succcessfully delivered to the receiver or failed.<br>See the sample request at <a href="https://samplefordevelopers.esms.vn/#20f85e1f-3d9e-4ff4-bc4f-8d9c9edbc88a">here</a>.<br>More details at <a href="../callback-url.md">here</a>.</td></tr><tr><td>SendingMode</td><td>string</td><td>false</td><td><h4>Sending Modes:</h4><p><strong>1. Default (Normal Sending):</strong><br>Messages are sent using the standard ZNS delivery mechanism.</p><p><strong>3. Exceed Quota Sending:</strong><br>Allows OA to send ZNS tagged messages exceeding the quota limits.<br><br></p><p><strong>Note:</strong><br>Exceed Quota Sending (SendingMode = 3) is only available for whitelisted OAs. Contact the Customer Support team for access.</p></td></tr></tbody></table>

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

{% tab title="789" %}
```json
{
    "CodeResult": "789",
    "CountRegenerate": 0,
    "ErrorMessage": "TemplateId is not config"
}
```

**The template is not configured on your account.**
{% endtab %}
{% endtabs %}



* Response body

| Parameter    | Type   | Description                                  |
| ------------ | ------ | -------------------------------------------- |
| CodeResult   | string | Response code.                               |
| SMSID        | string | The message id eSMS system.                  |
| ErrorMessage | string | The error message if the request is invalid. |

* _<mark style="color:yellow;">**The detail of error code can refer at**</mark>_ [**Table of error codes**](../table-of-error-codes.md) **.**
* _<mark style="color:yellow;">**Get the  sample of code for programing languagues to use in Postman refer at**</mark>_ [**Link  of code samples**](https://samplefordevelopers.esms.vn/#850974b9-12cf-46f5-946c-e8e15aa3585b)**.**
