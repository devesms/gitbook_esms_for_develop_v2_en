# Get callback data

This endpoint is used for getting the callback data in case of the callback URL is unable to receive the webhook.

If the request does not place the CallbackUrl, this endpoint will not return any information.

## HTTP request

\
<mark style="color:yellow;">**`POST`**</mark> [https://status-sms.esms.vn/ZaloCallback/GetCallback](https://status-sms.esms.vn/ZaloCallback/GetCallback)\


* **Content Type:** <mark style="color:orange;">application/json</mark>
* **Response Type:** <mark style="color:orange;">application/json</mark>

```json
curl --location 'https://status-sms.esms.vn/ZaloCallback/GetCallback' \
--header 'Content-Type: application/json' \
--data '{
    "ApiKey":"{{ApiKey}}",
    "SecretKey":"{{SecretKey}}",
    "ListRefid": [
        "{{Refid}}",
        "{{Refid}}",
        "{{Refid}}"
    ],
    "OAId": "{{OAId}}"
}'
```

* **Body request:**

<table><thead><tr><th width="137">Paramter</th><th width="152">Type</th><th width="160" data-type="checkbox">Required</th><th>Description</th></tr></thead><tbody><tr><td>ApiKey</td><td>string</td><td>true</td><td>Your API key.</td></tr><tr><td>SecretKey</td><td>string</td><td>true</td><td>Your Secret key.</td></tr><tr><td>ListRefid</td><td>string</td><td>true</td><td>The list of message ids that returned by ViHAT.<br>Maximum is 200 message ids per call.</td></tr><tr><td>OAId</td><td>string</td><td>true</td><td><p>Zalo OA Id is the Zalo Official Account Id of the organization. It can be obtained by accessing to the Zalo administrator page.</p><p><strong>Note: Pre-registration is required.</strong></p></td></tr></tbody></table>

***

* **Response:**

{% tabs %}
{% tab title="100" %}
```json
{
    "Code": 100,
    "Message": "Success",
    "Data_callback": [
        {
            "SMSID": "4a496110-9fd3-4838-ac8b-bcaa36616f7011",
            "SendFailed": 1,
            "SendSuccess": 0,
            "SendStatus": 5,
            "TotalPrice": 0.0,
            "TotalReceiver": 1,
            "TotalSent": 1,
            "RequestId": null,
            "TypeId": 25,
            "Telcoid": 1,
            "PhoneNumber": "0909090909",
            "CallbackUrl": "https://api.esms.vn/zalo-zns/zns/receive-callback",
            "Partnerids": "7984e9b198c40e9957d6",
            "ErrorInfo": "{\"error\":-124,\"message\":\"Access token is invalid\"}Object reference not set to an instance of an object.",
            "OAId": "1090257973118325189",
            "ZnsTempId": "228386"
        } 
                    ]
  } 
```

**Valid request.**
{% endtab %}
{% endtabs %}

* **Response body:**

<table><thead><tr><th width="168.33333333333331">Paramter</th><th width="158">Type</th><th>Description</th></tr></thead><tbody><tr><td>SMSID</td><td>string</td><td>Message id that returned by ViHAT.</td></tr><tr><td>SendFailed</td><td>string</td><td>Number of failed messages.</td></tr><tr><td>SendSuccess</td><td>string</td><td>Number of success messages.</td></tr><tr><td>SendStatus</td><td>string</td><td>Message status.<br>2: In process<br>5: Sent</td></tr><tr><td>TotalPrice</td><td>string</td><td>The cost of message.</td></tr><tr><td>TotalReceiver</td><td>string</td><td>Total receivers.</td></tr><tr><td>TotalSent</td><td>string</td><td>Total messages are sent.</td></tr><tr><td>RequestId</td><td>string</td><td>The id of client in the request.</td></tr><tr><td>TypeId</td><td>string</td><td><p>Type of message.</p><ul><li>Type 24: ZNS priority.</li></ul><ul><li>Type 25: ZNS normal.</li></ul></td></tr><tr><td>Telcoid</td><td>string</td><td><p>Mạng viễn thông của thuê bao nhận tin.<br>The telco of phone number.</p><ul><li>1: Viettel</li></ul><ul><li>2: Mobifone</li></ul><ul><li>3: Vinaphone</li></ul><ul><li>4: Vietnammobile</li></ul><ul><li>5: Gmobile</li></ul><ul><li>6: Itel</li></ul><ul><li>7: Reddi</li></ul></td></tr><tr><td>PhoneNumber</td><td>string</td><td>The phone number of receiver</td></tr><tr><td>CallbackUrl</td><td>string</td><td>The URL callback of client.</td></tr><tr><td>Partnerids</td><td>string</td><td>The message id of Zalo</td></tr><tr><td>ErrorInfo</td><td>string</td><td>The error info of request.</td></tr><tr><td>OAId</td><td>string</td><td><p>Zalo OA Id is the Zalo Official Account Id of the organization. It can be obtained by accessing to the Zalo administrator page.</p><p><strong>Note: Pre-registration is required.</strong></p></td></tr><tr><td>ZnsTempId</td><td>string</td><td>The ID of template for the OA that is registered and provided by eSMS at Zalo to partner.<br>Each template will have a specified structure of body.</td></tr></tbody></table>

{% hint style="info" %}
Note:

* Maximum is 200 message ids per call. Only 200 first message will be returned if it is larger than 200.
* TPS: 20.
{% endhint %}

* _<mark style="color:yellow;">**The detail of error code can refer at**</mark>_ [**Table of error codes**](../table-of-error-codes.md) **.**
* _<mark style="color:yellow;">**Get the  sample of code for programing languagues to use in Postman refer at**</mark>_ [**Link  of code samples**](https://samplefordevelopers.esms.vn/#850974b9-12cf-46f5-946c-e8e15aa3585b)**.**
