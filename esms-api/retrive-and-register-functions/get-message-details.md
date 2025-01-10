# Get message details

This endpoint is used for retriving the list of receivers by SmsId in last 7 days.

The response is the detail of each message including the message status.

## HTTP request

\
<mark style="color:green;">**`GET`**</mark> [http://rest.esms.vn/MainService.svc/json/GetSmsReceiverStatus\_get?\&ApiKey=\{{ApiKey\}}\&SecretKey=\{{SecretKey\}}\&RefId=\{{SMSID\}}](http://rest.esms.vn/MainService.svc/json/GetSmsReceiverStatus_get?\&ApiKey=\{{ApiKey\}}\&SecretKey=\{{SecretKey\}}\&RefId=\{{SMSID\}})

* **Response Type:** <mark style="color:orange;">application/json</mark>

```
curl --location --globoff 'https://rest.esms.vn/MainService.svc/json/GetSmsReceiverStatus_get?ApiKey={{ApiKey}}&SecretKey={{SecretKey}}&RefId={{SMSID}}'
```

* **Request body:**

<table><thead><tr><th width="139">Parameter</th><th width="131">Type</th><th width="149" data-type="checkbox">Required</th><th>Description</th></tr></thead><tbody><tr><td>ApiKey</td><td>string</td><td>true</td><td>Your API key.</td></tr><tr><td>SecretKey</td><td>string</td><td>true</td><td>Your Secret key.</td></tr><tr><td>RefId</td><td>string</td><td>true</td><td>The message id that returned by ViHAT</td></tr></tbody></table>



***

* **Response:**

{% tabs %}
{% tab title="100" %}
```json
{
    "CodeResult": "100",
    "ReceiverList": [
        {
            "IsSent": true,
            "NetworkName": "Viettel",
            "Phone": "0901888484",
            "Retry": 0,
            "SentResult": true
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
    "ErrorMessage": "Authorize Failed"
}
```

**Invalid credential.**
{% endtab %}
{% endtabs %}

* **Response body:**

| Paramter    | Type   | Description                                                                           |
| ----------- | ------ | ------------------------------------------------------------------------------------- |
| IsSent      | string | <p>The state of message:<br>true: Message is sent.<br>false: Message is not sent.</p> |
| NetworkName | string | The telco of phone number.                                                            |
| Phone       | string | The phone number of user.                                                             |
| Retry       | string | The number of retries.                                                                |
| SentResult  | string | <p>The result of message:<br>True: Success.<br>False: Failed.</p>                     |

* _<mark style="color:yellow;">**The detail of error code can refer at**</mark>_ [**Table of error codes**](../table-of-error-codes.md) **.**
* _<mark style="color:yellow;">**Get the  sample of code for programing languagues to use in Postman refer at**</mark>_ [**Link  of code samples**](https://samplefordevelopers.esms.vn/#850974b9-12cf-46f5-946c-e8e15aa3585b)**.**
