# The multichannel auto-generated OTP

This endpoint is ideal for sending the OTP using multichannel mechanism.

The message will switch to SMS in case of the ZNS message gets failed with the same OTP.

## HTTP request

\
<mark style="color:yellow;">**`POST`**</mark> [https://rest.esms.vn/MainService.svc/json/SendMessageAutoGenCode\_V5](http://rest.esms.vn/MainService.svc/json/SendMessageAutoGenCode_V5)

* **Content Type:** <mark style="color:orange;">application/json</mark>
* **Response Type:** <mark style="color:orange;">application/json</mark>

{% code overflow="wrap" %}
```json
curl --location 'https://rest.esms.vn/MainService.svc/json/SendMessageAutoGenCode_V5' \
--header 'Content-Type: application/json' \
--data '{
 "ApiKey": "{{ApiKey}}",
 "Phone": "{{Phone}}",
 "TimeAlive": "{{TimeAlive}}",
 "SecretKey": "{{SecretKey}}",
 "MultiChannelTempId": "{{MultiChannelTempId}}",
 "TypeId":"{{TypeId}}"
}'
```
{% endcode %}

* **Request body:**

<table><thead><tr><th width="207">Parameter</th><th width="124">Type</th><th width="143" data-type="checkbox">Required</th><th>Description</th></tr></thead><tbody><tr><td>ApiKey</td><td>string</td><td>true</td><td>Your API Key.</td></tr><tr><td>Phone</td><td>string</td><td>true</td><td>The phone number of receiver.</td></tr><tr><td>TimeAlive</td><td>string</td><td>false</td><td>The time-to-live of the OTP.<br>Unit of cal: <strong>minute</strong> <br>Do not pass this parameter, default validity is 5 minutes</td></tr><tr><td>SecretKey</td><td>string</td><td>true</td><td>Your Secret Key.</td></tr><tr><td>MultiChannelTempId</td><td>string</td><td>true</td><td>The Id vaue provided by ViHAT. <br>To use this endpoint, you must have the OA and brandname. <br>You have to send the ZNS and SMS template id to your saleman for creating.</td></tr><tr><td>TypeId</td><td>string</td><td>true</td><td>1: Only generate the OTP<br>2: Generate and send the OTP to phone.</td></tr></tbody></table>

***

* **Response**:&#x20;

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
    "CodeResult": "100",
    "CountRegenerate": 0,
    "SMSID": "ebe101db-87cd-4285-b97b-6a7a90455ded30"
}
```

**Invalid credential.**
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
* <mark style="color:orange;">**Use API Checkcode to check the validation of OTP. See it at**</mark> [**API Checkcode**](../other-apis/check-code.md)**.**&#x20;
