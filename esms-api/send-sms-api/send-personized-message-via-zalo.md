# Send personized message via Zalo

This endpoint is used for sending SMS by batch (1 request for multiple SMS) via Zalo with shared or personized content/properties.

It is ideal to send any kind of massive personalized announcement.

## HTTP request

\
<mark style="color:yellow;">**`POST`**</mark> [https://rest.esms.vn/MainService.svc/json/Send\_zns\_bulk\_v4\_post\_json/](http://rest.esms.vn/MainService.svc/json/Send_zns_bulk_v4_post_json/)



* **Content Type:** <mark style="color:orange;">application/json</mark>
* **Response Type:** <mark style="color:orange;">application/json</mark>

```json
curl --location 'https://rest.esms.vn/MainService.svc/json/Send_zns_bulk_v4_post_json/' \
--header 'Content-Type: application/json' \
--data '{
    "ApiKey": "{{ApiKey}}",
    "SecretKey": "{{SecretKey}}",
    "campaignid": "Chiến dịch 1",
    "OAID": "4097311281936189049",
    "TempID": "267247",
    "Sandbox": "0",
    "CallbackUrl": "https://esms.vn/webhook/",
    "Data": [
        {
            "Phone": "0901888484",
            "RequestId": "96accf59-0c41-4bc7-a5c1",
            "Params": [ "Chị A", "Gội đầu", "KH001", "19/03/2025" ]
        },
        {
            "Phone": "0918238965",
            "RequestId": "96accf59-0c41-4bc7-a5c2",
            "Params": [ "Chị B", "Uốn", "KH002", "19/03/2025" ]
        },
        {
            "Phone": "0765418062",
            "RequestId": "96accf59-0c41-4bc7-a5c3",
            "Params": [ "Chị C", "Nhuộm", "KH003", "19/03/2025" ]
        }
    ]
}'
```

* Request body

<table><thead><tr><th width="155">Paramter</th><th width="124">Type</th><th width="141" data-type="checkbox">Required</th><th>Description</th></tr></thead><tbody><tr><td>ApiKey </td><td>string</td><td>true</td><td>Your API Key.</td></tr><tr><td>SecretKey </td><td>string</td><td>true</td><td>Your Secret Key.</td></tr><tr><td>TempID </td><td>string</td><td>true</td><td>The ID of template for the OA that is registered and provided by eSMS at Zalo to partner.<br>Each template will have a specified structure of body.</td></tr><tr><td>Data</td><td>Array</td><td>true</td><td>An array of objects containing information about each message you want to send.<br>Note: The array has a maximum size of 500 elements.</td></tr><tr><td>Data: Phone</td><td>string</td><td>true</td><td>The phone number of receivers.</td></tr><tr><td>Data: RequestId</td><td>string</td><td>false</td><td>Partner Message ID, used to check whether this ID has been previously received by the esms system.<br>Ex: <code>RequestId=123456</code>.</td></tr><tr><td>Data: Params </td><td>string</td><td>true</td><td><p>The values that need to pass according to the template variables.</p><p>Giá trị cần truyền cho các biến trong Template</p><p> *Note:</p><ol><li>The values must be placed in the correct order with the registered template.</li><li>If the parameter is duplicated, just place one.<br></li></ol></td></tr><tr><td>SendDate</td><td>string</td><td>false</td><td>Scheduler the message to the receiver.<br>If it's empty, the message will be instantly sent to the receiver.<br>Format: <strong>yyyy-mm-dd hh:MM:ss</strong></td></tr><tr><td>OAID </td><td>string</td><td>true</td><td><p>Zalo OA Id is the Zalo Official Account Id of the organization. It can be obtained by accessing to the Zalo administrator page.</p><p><strong>Note: Pre-registration is required.</strong></p></td></tr><tr><td>CallbackUrl</td><td>string</td><td>false</td><td>The webhook URL that will receive the status of message after it processed to the operator. It is used for determine whether the SMS is succcessfully delivered to the receiver or failed.<br>See the sample request at <a href="https://samplefordevelopers.esms.vn/#20f85e1f-3d9e-4ff4-bc4f-8d9c9edbc88a">here</a>.<br>More details at <a href="../callback-url.md">here</a>.</td></tr></tbody></table>

***

* **Response:**

{% tabs %}
{% tab title="100" %}
```json

{
    "CodeResult": "100",
    "Message": "Sucess",
    "TotalSuccess": 2,
    "detail": [
        {
            "CodeResult": "100",
            "Phone": "{Phone}",
            "SMSID": "a037b928-cb7e-4bfc-bdf9-0286318163aa264"
        },
        {
            "CodeResult": "100",
            "Phone": "{Phone}",
            "SMSID": "b83ff06e-8989-4b0d-818e-795b96699e86264"
        }
    ]
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

**The template is not configured on your account and OA.**
{% endtab %}
{% endtabs %}

* **Response body**

<table><thead><tr><th width="209">Parameter</th><th width="146">Type</th><th>Description</th></tr></thead><tbody><tr><td>CodeResult</td><td>string</td><td>Response code</td></tr><tr><td>Message</td><td>string</td><td>The error message if the request is invalid.</td></tr><tr><td>TotalSuccess</td><td>string</td><td>Number of successfully requests.</td></tr><tr><td>detail : CodeResult</td><td>string</td><td>The detail response code</td></tr><tr><td>detail : Phone</td><td>string</td><td>Phone number of receiver</td></tr><tr><td>detail : SMSID</td><td>string</td><td>The message id corresponding to the phone number.</td></tr></tbody></table>

* _<mark style="color:yellow;">**The detail of error code can refer at**</mark>_ [**Table of error codes**](../table-of-error-codes.md) **.**
* _<mark style="color:yellow;">**Get the  sample of code for programing languagues to use in Postman refer at**</mark>_ [**Link  of code samples**](https://samplefordevelopers.esms.vn/#850974b9-12cf-46f5-946c-e8e15aa3585b)**.**
