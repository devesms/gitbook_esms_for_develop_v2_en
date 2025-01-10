---
description: >-
  API dùng để gửi tin Quảng cáo đến khách hàng. Mỗi request tối thiểu 30 số để
  được duyệt tin và tối đa 5000 số.
---

# Send adveritising message

Sending a POST request on this endpoint allows to send bulk advertising SMS (maximum 5000 receivers per request).&#x20;

Personalized content is ideal for sending marketing campaigns or any mass personalized announcement.

## **HTTP request**&#x20;



\
<mark style="color:yellow;">**`POST`**</mark> [https://rest.esms.vn/MainService.svc/json/SendMultipleSMSBrandname\_json/](http://rest.esms.vn/MainService.svc/json/SendMultipleSMSBrandname_json/)\


* **Content Type:** <mark style="color:orange;">application/json</mark>
* **Response Type:** <mark style="color:orange;">application/json</mark>

```json
curl --location 'https://rest.esms.vn/MainService.svc/json/SendMultipleSMSBrandname_json/' \
--header 'Content-Type: application/json' \
--data '{
    "ApiKey": "{{SecretKey}}",
    "SecretKey": "{{SecretKey}}",
    "Brandname": "{{Brandname}}",
    "Content": "{{Content}}",
    "Phones": [
        "{{Phones}}",
        "{{Phones}}",
        "{{Phones}}"
    ],
    "SmsType": "1",
    "SendDate": "{{SendDate}}",
    "CallbackUrl": "{{CallbackUrl}}",
    "Sandbox":"{{Sandbox}}"
}'
```

* **Cấu trúc body của request:**

<table><thead><tr><th width="170">Paramter</th><th width="116">Type</th><th width="109" data-type="checkbox">Required</th><th>Description</th></tr></thead><tbody><tr><td>ApiKey </td><td>string</td><td>true</td><td>Your API Key.</td></tr><tr><td>SecretKey </td><td>string</td><td>true</td><td>Your Secret Key.</td></tr><tr><td>Content </td><td>string</td><td>true</td><td>The personized or marketing content.</td></tr><tr><td>SmsType </td><td>string</td><td>true</td><td>Message type:<br>1: Advertising/marking message.</td></tr><tr><td>Brandname </td><td>string</td><td>true</td><td>The name of the sender is shown in the header of the customer's message. <br><strong>Pre-registration is required.</strong></td></tr><tr><td>Phones </td><td>array</td><td>true</td><td>The phone number of receivers.</td></tr><tr><td>SendDate</td><td>string</td><td>false</td><td>Schedule the time when the message to the receiver.<br>If it's empty, the message will be instantly sent to the receiver.<br>Format: <strong>yyyy-mm-dd hh:MM:ss</strong></td></tr><tr><td>CallbackUrl</td><td>string</td><td>false</td><td>The webhook URL that will receive the status of message after it processed to the operator. It is used for determine whether the SMS is succcessfully delivered to the receiver or failed.<br>See the sample request at <a href="https://samplefordevelopers.esms.vn/#20f85e1f-3d9e-4ff4-bc4f-8d9c9edbc88a">here</a>.<br>More detail at <a href="../callback-url.md">here</a>.</td></tr><tr><td>Sandbox</td><td>string</td><td>false</td><td>Sandbox option value (<strong>default is 0</strong>):<br>1: For testing purpose to verify the validation of the request. Message is not charged and sent to the receiver.<br>0: Message will be processed to the receiver properly.</td></tr></tbody></table>

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
```json
{
    "CodeResult": "107",
    "CountRegenerate": 0,
    "ErrorMessage": "Each request has at least 30 numbers to be approved"
}
```

**At least 30 receivers per request.**
{% endtab %}

{% tab title="124" %}
```json
{
    "CodeResult": "124",
    "CountRegenerate": 0,
    "ErrorMessage": "Request exist 1"
}
```

**Duplicate request id.**
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

