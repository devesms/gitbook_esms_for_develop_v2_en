# Get SMS by SMSID

This endpoint is used for retriving the message status that sent to ViHAT in last 7 days.

## HTTP request

\
<mark style="color:green;">**`GET`**</mark> [https://rest.esms.vn/MainService.svc/json/GetSendStatus?RefId=\{{SMSID\}}\&ApiKey=\{{ApiKey\}}\&SecretKey=\{{SecretKey\}}](https://rest.esms.vn/MainService.svc/json/GetSendStatus?RefId=\{{SMSID\}}\&ApiKey=\{{ApiKey\}}\&SecretKey=\{{SecretKey\}})

* **Response Type:** <mark style="color:orange;">application/json</mark>



```json
curl --location --globoff 'http://rest.esms.vn/MainService.svc/json/GetSendStatus?RefId={{SMSID}}&ApiKey={{ApiKey}}&SecretKey={{SecretKey}}'
```

* **Request body:**

<table><thead><tr><th width="139">Parameter</th><th width="129">Type</th><th width="155" data-type="checkbox">Required</th><th>Description</th></tr></thead><tbody><tr><td>RefId</td><td>string</td><td>true</td><td>The message id returned by ViHAT</td></tr><tr><td>ApiKey</td><td>string</td><td>true</td><td>Your API key.</td></tr><tr><td>SecretKey</td><td>string</td><td>true</td><td>Your Secret key.</td></tr></tbody></table>

***

* **Response:**

{% tabs %}
{% tab title="100" %}
```
{
    "CodeResponse": "100",
    "SMSID": "434a124c-7818-4f45-bdf2-7f7b07fff210100",
    "SendFailed": 0,
    "SendStatus": 5,
    "SendSuccess": 1,
    "TotalPrice": 850.0000,
    "TotalReceiver": 1,
    "TotalSent": 1
}
```

**Valid request.**
{% endtab %}

{% tab title="101" %}
```json
{
    "CodeResponse": "101",
    "SMSID": "47756317-0cbe-494a-9d02-c85703a1baff20"
}
```

**Invalid request.**
{% endtab %}
{% endtabs %}

* **Response body:**

<table><thead><tr><th width="174">Paramter</th><th width="155">Type</th><th>Description</th></tr></thead><tbody><tr><td>CodeResponse</td><td>string</td><td>Response code.</td></tr><tr><td>SMSID</td><td>string</td><td>The message id returned by ViHAT</td></tr><tr><td>SendFailed</td><td>string</td><td>Total of failed messages.</td></tr><tr><td>SendStatus</td><td>string</td><td>Message status<br>1: In review.<br>2: Waiting.<br>5: Send to operator.</td></tr><tr><td>SendSuccess</td><td>string</td><td>Total of success messages.</td></tr><tr><td>TotalPrice</td><td>string</td><td>The cost of submit.</td></tr><tr><td>TotalReceiver</td><td>string</td><td>Total phone numbers.</td></tr><tr><td>TotalSent</td><td>string</td><td>Total of phone numbers that sent to operator.</td></tr></tbody></table>

* _<mark style="color:yellow;">**The detail of error code can refer at**</mark>_ [**Table of error codes**](../table-of-error-codes.md) **.**
* _<mark style="color:yellow;">**Get the  sample of code for programing languagues to use in Postman refer at**</mark>_ [**Link  of code samples**](https://samplefordevelopers.esms.vn/#850974b9-12cf-46f5-946c-e8e15aa3585b)**.**
