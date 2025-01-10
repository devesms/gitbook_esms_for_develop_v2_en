# Send Zalo messages to request user's information

## HTTP request

\
<mark style="color:yellow;">**POST**</mark> [https://rest.esms.vn/MainService.svc/json/SendZaloFollowerMessage\_V5\_post\_json/](http://rest.esms.vn/MainService.svc/json/SendZaloFollowerMessage_V5_post_json/)



* **Content Type:** <mark style="color:orange;">application/json</mark>
* **Response Type:** <mark style="color:orange;">application/json</mark>

```json
curl --location 'https://rest.esms.vn/MainService.svc/json/SendZaloFollowerMessage_V5_post_json/' \
--header 'Content-Type: application/json' \
--data '{
"ApiKey": "{{ApiKey}}",
"SecretKey": "{{SecretKey}}",
"OAID": "{{OAID}}",
"CallbackUrl":"{{CallbackURL}}",
    "Payload": {
        "recipient": {
            "user_id": "{{UserID}}"
        },
        "message": {
            "attachment": {
                "type": "template",
                "payload": {
                    "template_type": "request_user_info",
                    "elements": [
                        {
                            "title": "{{Title}}",
                            "subtitle": "{{Subtitle}}",
                            "image_url": "{{ImageURL}}"
                        }
                    ]
                }
            }
        }
    }
}'
```



* **Body request**

<table><thead><tr><th width="135">Parameter</th><th width="120">Type</th><th width="152" data-type="checkbox">Required</th><th>Description</th></tr></thead><tbody><tr><td>ApiKey</td><td>string</td><td>true</td><td>Your API Key</td></tr><tr><td>SecretKey</td><td>string</td><td>true</td><td>Your Secret Key</td></tr><tr><td>OAID</td><td>string</td><td>true</td><td><p>Zalo OA Id is the Zalo Official Account Id of the organization. It can be obtained by accessing to the Zalo administrator page.</p><p><strong>Note: Pre-registration is required.</strong></p></td></tr><tr><td>User_id</td><td>string</td><td>true</td><td>The identification value of user at Zalo.</td></tr><tr><td>Title</td><td>string</td><td>true</td><td>The title of template.<br>Note: Max length is 100.</td></tr><tr><td>Subtitle</td><td>string</td><td>true</td><td>The subtitle of template.<br>Note: Max length is 500.</td></tr><tr><td>ImageUrl</td><td>string</td><td>true</td><td>The image URL. Only accept .PNG or .JPG file</td></tr><tr><td>CallbackUrl</td><td></td><td>false</td><td><p>The webhook URL that will receive the status of message after it processed to the operator. It is used for determine whether the SMS is succcessfully delivered to the receiver or failed.</p><p><br>See the sample request at <a href="https://samplefordevelopers.esms.vn/#20f85e1f-3d9e-4ff4-bc4f-8d9c9edbc88a">here</a>.<br>More detail at <a href="../callback-url.md">here</a>.</p></td></tr></tbody></table>

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
{% endtabs %}

* **Response body**

| Parameter    | Type   | Description                                  |
| ------------ | ------ | -------------------------------------------- |
| CodeResult   | string | Response code.                               |
| SMSID        | string | The message id eSMS system.                  |
| ErrorMessage | string | The error message if the request is invalid. |

* _<mark style="color:yellow;">**The detail of error code can refer at**</mark>_ [**Table of error codes**](../table-of-error-codes.md) **.**
* _<mark style="color:yellow;">**Get the  sample of code for programing languagues to use in Postman refer at**</mark>_ [**Link  of code samples**](https://samplefordevelopers.esms.vn/#850974b9-12cf-46f5-946c-e8e15aa3585b)**.**
