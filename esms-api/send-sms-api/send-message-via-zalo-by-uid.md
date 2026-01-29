---
hidden: true
---

# Send message via Zalo by UID

## HTTP request

\
<mark style="color:yellow;">**`POST`**</mark> [https://rest.esms.vn//MainService.svc/json/SendZaloMessage\_V6/zalo\_uid/](https://rest.esms.vn/MainService.svc/json/SendZaloMessage_V6/zalo_uid/)

* **Content Type:** <mark style="color:orange;">application/json</mark>
* **Response Type:** <mark style="color:orange;">application/json</mark>

{% code overflow="wrap" %}
```json
curl --location 'https://rest.esms.vn//MainService.svc/json/SendZaloMessage_V6/zalo_uid/' \
--header 'Content-Type: application/json' \
--data '{
    "ApiKey": "APIKEYCUABAN",
    "SecretKey": "SECRETKEYCUABAN",
    "OAID": "4097311281936189049",
    "ZaloUid": "0901888484",
    "TempData": {
        "customer_name": "Đinh Thái Hà",
        "order_code": "HD00001",
        "address": "140-142 Đường Số 1, KDC Vạn Phúc, Hiệp Bình Phước, Thủ Đức",
        "phone": "0901888484",
        "email": "dinhthaiha@vihatgroup.com",
        "product_name": "Gói duy trì OA Zalo Premium 1 năm",
        "quantity": "1",
        "payment_amount": "4308000",
        "delivery_date": "01/08/2024"
    },
    "TempID":  "200607",
    "campaignid":  "Xác nhận mua hàng",
    "RequestId": "96accf59-0c41-4bc7-a5c4-4a466c2e41c2",
    "CallbackUrl": "https://esms.vn/webhook/"
}'
```
{% endcode %}

* **Request body**

<table><thead><tr><th width="152">Parameter</th><th width="128">Type</th><th width="105" data-type="checkbox">Required</th><th>Description</th></tr></thead><tbody><tr><td>ZaloUid</td><td>string</td><td>true</td><td>The Zalo Userid of receivers.</td></tr><tr><td>ApiKey</td><td>string</td><td>true</td><td>Your API Key.</td></tr><tr><td>SecretKey</td><td>string</td><td>true</td><td>Your Secret Key.</td></tr><tr><td>OAID</td><td>string</td><td>true</td><td><p>Zalo OA Id is the Zalo Official Account Id of the organization. It can be obtained by accessing to the Zalo administrator page.</p><p><strong>Note: Pre-registration is required.</strong></p></td></tr><tr><td>TempData</td><td>Json object</td><td>true</td><td>The dynamic json object of the template that is registered at Zalo. <br>The template data structure is specified separatedly for each teamplate.</td></tr><tr><td>SendDate</td><td>string</td><td>false</td><td>Schedule the time when the message to the receiver.<br>If it's empty, the message will be instantly sent to the receiver.<br>Format: <strong>yyyy-mm-dd hh:MM:ss</strong></td></tr><tr><td>TempID </td><td>string</td><td>true</td><td>The ID of template for the OA that is registered and provided by eSMS at Zalo to partner.<br>Each template will have a specified structure of body.</td></tr><tr><td>campaignid</td><td>string</td><td>false</td><td>The campaign name of request</td></tr><tr><td>RequestId</td><td>string</td><td>false</td><td>Partner ID passed to block duplicates and check if needed.<br>Maximum length 50 characters.<br>Each RequestId passed is valid for blocking for 24 hours.</td></tr><tr><td>Sandbox</td><td>string</td><td>false</td><td>Sandbox option value (<strong>default is 0</strong>):<br>1: For testing purpose to verify the validation of the request. Message is not charged and sent to the receiver.<br>0: Message will be processed to the receiver properly.</td></tr><tr><td>CallbackUrl</td><td>string</td><td>false</td><td>The webhook URL that will receive the status of message after it processed to the operator. It is used for determine whether the SMS is succcessfully delivered to the receiver or failed.<br>See the sample request at <a href="https://samplefordevelopers.esms.vn/#20f85e1f-3d9e-4ff4-bc4f-8d9c9edbc88a">here</a>.<br>More details at <a href="../callback-url.md">here</a>.</td></tr></tbody></table>

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
