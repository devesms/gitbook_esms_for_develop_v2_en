# Send multi-channel message via Zalo and SMS

This endpoint is used for sending multi-channel SMS via Zalo and SMS by orderding.

It is ideal to send the personalized messages for use-cases like notifications, alerting or marketing for example with high delivery rate.

## HTTP request

\
<mark style="color:yellow;">**`POST`**</mark> [https://rest.esms.vn/MainService.svc/json/MultiChannelMessage/](https://rest.esms.vn/MainService.svc/json/MultiChannelMessage/)\


* **Content Type:** <mark style="color:orange;">application/json</mark>
* **Response Type:** <mark style="color:orange;">application/json</mark>

{% code overflow="wrap" %}
```json
curl --location 'https://rest.esms.vn/MainService.svc/json/MultiChannelMessage/' \
--header 'Content-Type: application/json' \
--data '{
    "ApiKey": "{{ApiKey}}",
    "SecretKey": "{{SecretKey}}",
    "Phone": "{{Phone}}",
    "Channels": [
        "zalo",
        "sms"
    ],
    "Data": [
        {
            "TempID": "{{TempID}}",
            "Params": ["{{param1}}","{{param2}}","{{param3}}"],
            "OAID": "{{OAID}}",
            "campaignid": "{{campaignid}}",
            "CallbackUrl": "{{CallbackUrl}}",
            "RequestId":"{{RequestId}}",
            "Sandbox":"{{Sandbox}}"
        },
        {
            "Content": "{{Content}}",
            "IsUnicode": "{{IsUnicode}}",
            "SmsType": "{{SmsType}}",
            "Brandname": "{{Brandname}}",
            "CallbackUrl": "{{CallbackUrl}}",
            "RequestId":"{{RequestId}}",
            "Sandbox":"{{Sandbox}}"
        }
    ]
}'
```
{% endcode %}

* **Request body**

<table><thead><tr><th width="152">Parameter</th><th width="135">Type</th><th width="147" data-type="checkbox">Required</th><th>Description</th></tr></thead><tbody><tr><td>ApiKey </td><td>string</td><td>true</td><td>Your API Key.</td></tr><tr><td>SecretKey</td><td>string</td><td>true</td><td>Your Secret Key.</td></tr><tr><td>Phone</td><td>string</td><td>true</td><td>The phone number of receivers.</td></tr><tr><td>Params</td><td>array</td><td>true</td><td><p><br>The values that need to pass according to the template variables.</p><p>Giá trị cần truyền cho các biến trong Template <br>*Notes:</p><ol><li>The values must be placed in the correct order with the registered template.</li><li>If the parameter is duplicated, just place one.</li></ol></td></tr><tr><td>TempID</td><td>string</td><td>true</td><td>Template của The ID of template for the OA that is registered and provided by eSMS at Zalo to partner.<br>Each template will have a specified structure of body.</td></tr><tr><td>OAID</td><td>string</td><td>true</td><td><p>Zalo OA Id is the Zalo Official Account Id of the organization. It can be obtained by accessing to the Zalo administrator page.</p><p><strong>Note: Pre-registration is required.</strong></p></td></tr><tr><td>RequestId</td><td>string</td><td>false</td><td>The identification value for the request to prevent the the request from duplicated.</td></tr><tr><td>campaignid</td><td>string</td><td>false</td><td>The campaign name of request.</td></tr><tr><td>CallbackUrl</td><td>string</td><td>false</td><td>The webhook URL that will receive the status of message after it processed to the operator. It is used for determine whether the SMS is succcessfully delivered to the receiver or failed.<br>See the sample request at <a href="https://samplefordevelopers.esms.vn/#20f85e1f-3d9e-4ff4-bc4f-8d9c9edbc88a">here</a>.<br>More details at <a href="../callback-url.md">here</a>.</td></tr><tr><td>Content</td><td>string</td><td>true</td><td>The OTP or marketing content.</td></tr><tr><td>IsUnicode</td><td>string</td><td>false</td><td><p>Message charset value (<strong>default is 0</strong>):<br>1: Unicode.</p><p>0: Non-Unicode.</p></td></tr><tr><td>SmsType </td><td>string</td><td>true</td><td>Message type:<br>2: Customer care message</td></tr><tr><td>Brandname</td><td>string</td><td>true</td><td>The name of the sender is shown in the header of the customer's message. <br><strong>Pre-registration is required.</strong></td></tr><tr><td>Sandbox</td><td>string</td><td>false</td><td>Sandbox option value (<strong>default is 0</strong>):<br>1: For testing purpose to verify the validation of the request. Message is not charged and sent to the receiver.<br>0: Message will be processed to the receiver properly.</td></tr></tbody></table>

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

**Invlid credential.**
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

* **Response body**

| Parameter    | Type   | Description                                  |
| ------------ | ------ | -------------------------------------------- |
| CodeResult   | string | Response code.                               |
| SMSID        | string | The message id of eSMS system.               |
| ErrorMessage | string | The error message if the request is invalid. |

* _<mark style="color:yellow;">**The detail of error code can refer at**</mark>_ [**Table of error codes**](../table-of-error-codes.md) **.**
* _<mark style="color:yellow;">**Get the  sample of code for programing languagues to use in Postman refer at**</mark>_ [**Link  of code samples**](https://samplefordevelopers.esms.vn/#850974b9-12cf-46f5-946c-e8e15aa3585b)**.**
