# Get ZNS status information

This function is used to retrieve the state of the ZNS message.

{% hint style="info" %}
**Note: The speed limit for this API is 30 requests per second.**
{% endhint %}

## HTTP request

\
<mark style="color:yellow;">**`POST`**</mark> [http://rest.esms.vn/MainService.svc/json/GetZaloMessageStatus](http://rest.esms.vn/MainService.svc/json/GetZaloMessageStatus)<br>

* **Content Type:** <mark style="color:orange;">application/json</mark>
* **Response Type:** <mark style="color:orange;">application/json</mark>

```json
curl --location 'http://rest.esms.vn/MainService.svc/json/GetZaloMessageStatus' \
--header 'Content-Type: application/json' \
--data '{
    "ApiKey": "{{ApiKey}}",
    "SecretKey": "{{SecretKey}}",
    "OAID": "{{OAID}}",
    "MessageId": "{{MessageId}}"
}'
```

* **Request body:**

<table><thead><tr><th width="167">Paramter</th><th width="126">Type</th><th width="134" data-type="checkbox">Required</th><th>Description</th></tr></thead><tbody><tr><td>ApiKey</td><td>string</td><td>true</td><td>Your API key.</td></tr><tr><td>SecretKey</td><td>string</td><td>true</td><td>Your Secret key.</td></tr><tr><td>OAID</td><td>string</td><td>true</td><td>Zalo OA ID is the ID of the business's Zalo Official Account.<br>The business needs to log in to the Zalo OA management page to get this Zalo OA ID.<br><strong>Note: registration is required before use.</strong></td></tr><tr><td>MessageId</td><td>string</td><td>true</td><td>The ID of the notification for which you need to retrieve ZNS status information (which is the Partnerids returned in the Zalo message callback information retrieval function)</td></tr></tbody></table>

***

* **Response:**

{% tabs %}
{% tab title="100" %}
```json
{
    "CodeResult": "100",
    "Data": {
        "delivery_time": "1767678030984",
        "message": "The message was delivered to the user's phone",
        "status": 1
    },
    "ErrorMessage": "success. "
}


```

**Valid request.**
{% endtab %}
{% endtabs %}

* **Response body:**

<table><thead><tr><th width="204">Paramter</th><th width="166">Type</th><th>Description</th></tr></thead><tbody><tr><td>CodeResult</td><td>string</td><td>Response code.</td></tr><tr><td>ErrorMessage</td><td>string</td><td>The message error in case of invalid request.</td></tr><tr><td>Data</td><td>string</td><td>Status information for the ZNS notification.</td></tr></tbody></table>

* **Structure of each object's attributes in the data:**

| Paramter       | Type   | Description                                                                                                                                                                                                                                                    |
| -------------- | ------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| delivery\_time | string | The time the user's device receives the ZNS notification.                                                                                                                                                                                                      |
| message        | string | <p>Description of the notification state. The return values are:<br>-1: The message does not exist<br>0: The message is pushed successfully to Zalo server but has not yet delivered to user’s phone<br>1: The message was delivered to the user's phone</p> |
| status         | int    | Status of the ZNS notification.                                                                                                                                                                                                                                |

* _<mark style="color:yellow;">**The detail of error code can refer at**</mark>_ [**Table of error codes**](../table-of-error-codes.md) **.**
* _<mark style="color:yellow;">**Get the  sample of code for programing languagues to use in Postman refer at**</mark>_ [**Link  of code samples**](https://samplefordevelopers.esms.vn/#cab8ca81-d83a-46e5-ab19-b58f29a6f656)**.**
