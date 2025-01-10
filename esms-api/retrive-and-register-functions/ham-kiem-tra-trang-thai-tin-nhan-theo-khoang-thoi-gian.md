# Get the message status

This endpoint is ideal for retriving the SMS data in a time range.

## HTTP request

\
<mark style="color:yellow;">**`POST`**</mark> [https://rest.esms.vn/MainService.svc/json/GetSmsSentData\_V2](http://rest.esms.vn/MainService.svc/json/GetSmsSentData_V2')

* **Content Type:** <mark style="color:orange;">application/json</mark>
* **Response Type:** <mark style="color:orange;">application/json</mark>

```json
curl --location 'https://rest.esms.vn/MainService.svc/json/GetSmsSentData_V2' \
--header 'Content-Type: application/json' \
--data '{
    "ApiKey":"{{ApiKey}}",
    "SecretKey":"{{SecretKey}}",
    "SmsType":"{{SmsType}}",
    "From": "{{DateFrom}}",
    "To":"{{DateTo}}",
    "Page":{{Page}},
    "PageSize":{{PageSize}}
}'
```

* **Body request:**

<table><thead><tr><th width="172">Parameter</th><th width="133">Type</th><th width="180" data-type="checkbox">Required</th><th>Description</th></tr></thead><tbody><tr><td>ApiKey</td><td>string</td><td>true</td><td>Your API Key.</td></tr><tr><td>SecretKey</td><td>string</td><td>true</td><td>Your Secret Key.</td></tr><tr><td>From </td><td>string</td><td>true</td><td>Start date<br>Format: <strong>yyyy-MM-dd HH:mm:ss</strong></td></tr><tr><td>To</td><td>string</td><td>true</td><td>End date<br>Format: <strong>yyyy-MM-dd HH:mm:ss</strong></td></tr><tr><td>Page</td><td>string</td><td>true</td><td>The start page.</td></tr><tr><td>PageSize</td><td>string</td><td>true</td><td><br>The number of SMS per page. Max: 500 SMS</td></tr><tr><td>SmsType</td><td>string</td><td>true</td><td>Type of SMS<br>1: Advertising SMS.<br>2: Customer care SMS.<br>8: Fixed number.<br>23: Viber OTT.<br>24: Priority ZNS.<br>25: Normally ZNS.<br>26: Zalo Follower.</td></tr></tbody></table>

***

* **Response:**

{% tabs %}
{% tab title="100" %}
```
{
    "CodeResult": "100",
    "CountTotal": 2
    "SentData": [
        {
            "Campaign": "Chiến dịch 02/10/2023",
            "Content": "Cam on quy khach da su dung dich vu cua chung toi. Chuc quy khach mot ngay tot lanh!",
            "Phone": "0901888484",
            "ReferenceId": "35781d6c25524e40a035c26663189549",
            "SellPrice": 345.0,
            "SendResult": 0,
            "SendStatus:5,
            "SentTime": "/Date(1705484048995+0700)/",
            "SmsId": 29028845,
            "SmsType": 2
        },
        {
            "Campaign": "Chiến dịch 02/10/2023",
            "Content": "Cam on quy khach da su dung dich vu cua chung toi. Chuc quy khach mot ngay tot lanh!",
            "Phone": "0901888484",
            "ReferenceId": "0aac72e0-ba9b-4348-8530-d18d105778db18",
            "SellPrice": 790.0000,
            "SendResult": 1,
            "SendStatus:5,
            "SentTime": "/Date(1705484048995+0700)/",
            "SmsId": 29028845,
            "SmsType": 2
        }
    ]
```

**Valid request.**
{% endtab %}

{% tab title="101" %}
```json
{
    "CodeResult": "101",
    "ErrorMessage": "Authorize Failed."
}
```

**Invalid credentials.**
{% endtab %}
{% endtabs %}

* **Response body:**

| Parameter    | Type   | Description                                                                                                                                                              |
| ------------ | ------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
|  CodeResult  | string |  Response code.                                                                                                                                                          |
| CountTotal   | string | The total SMS in this period.                                                                                                                                            |
| Campaign     | string | Campaign name.                                                                                                                                                           |
| Content      | string | The message content                                                                                                                                                      |
| Phone        | string | The phone number of receiver.                                                                                                                                            |
| RefercenceId | string | The id that returned on sending function.                                                                                                                                |
| Sellprice    | string | Unit price of message.                                                                                                                                                   |
| SendResult   | string | <p>State of message.</p><p>1: Success<br>0: Failed<br>2: Not acknowdege</p>                                                                                              |
| SendStatus   | string | <p>0: Composing<br>1: On review.<br>2: Enqueue.<br>4: Rejected.<br>5: SENT.<br>7: SENT (waiting for last result)</p>                                                     |
| SentTime     | string | The time that message is sent out.                                                                                                                                       |
| SmsId        | string | ID of message in portal.                                                                                                                                                 |
| SmsType      | string | <p>Type of SMS<br>1: Advertising SMS.<br>2: Customer care SMS.<br>8: Fixed number.<br>23: Viber OTT.<br>24: Priority ZNS.<br>25: Normally ZNS.<br>26: Zalo Follower.</p> |

* _<mark style="color:yellow;">**The detail of error code can refer at**</mark>_ [**Table of error codes**](../table-of-error-codes.md) **.**
* _<mark style="color:yellow;">**Get the  sample of code for programing languagues to use in Postman refer at**</mark>_ [**Link  of code samples**](https://samplefordevelopers.esms.vn/#850974b9-12cf-46f5-946c-e8e15aa3585b)**.**
