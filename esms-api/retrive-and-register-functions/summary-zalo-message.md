# Summary Zalo message

## HTTP request

\
<mark style="color:yellow;">**`POST`**</mark> [https://rest.esms.vn/MainService.svc/json/SummaryZaloMessage\_V4\_post\_json/](https://rest.esms.vn/MainService.svc/json/SummaryZaloMessage_V4_post_json/)\


* **Content Type:** <mark style="color:orange;">application/json</mark>
* **Response Type:** <mark style="color:orange;">application/json</mark>

```json
curl --location 'https://rest.esms.vn/MainService.svc/json/SummaryZaloMessage_V4_post_json/' \
--header 'Content-Type: application/json' \
--data '{
    "ApiKey": "{{ApiKey}}",
    "SecretKey": "{{SecretKey}}",
    "Phone": "{{Phone}}",
    "Params": [
        "{{value1}}",
        "{{value2}}",
        "{{value3}}"
    ],
    "TempID": "{{TempID}}",
    "OAID": "{{OAID}}"
}'
```

* **Request body:**

<table><thead><tr><th width="146">Tham số</th><th width="132">Kiểu dữ liệu </th><th width="143" data-type="checkbox">Tính bắt buộc</th><th>Mô tả</th></tr></thead><tbody><tr><td>ApiKey</td><td>string</td><td>true</td><td>Your API Key.</td></tr><tr><td>SecretKey</td><td>string</td><td>true</td><td>Your Secret Key.</td></tr><tr><td>Phone</td><td>string</td><td>true</td><td>The phone number of receivers.</td></tr><tr><td>Params</td><td>string</td><td>true</td><td><p></p><p>The values that need to pass according to the template variables.<br>*Notes:</p><ol><li>The values must be placed in the correct order with the registered template.</li><li>If the parameter is duplicated, just place one.</li></ol></td></tr><tr><td>TempID</td><td>string</td><td>true</td><td>Template của The ID of template for the OA that is registered and provided by eSMS at Zalo to partner.<br>Each template will have a specified structure of body.</td></tr><tr><td>OAID</td><td>string</td><td>true</td><td><p>Zalo OA Id is the Zalo Official Account Id of the organization. It can be obtained by accessing to the Zalo administrator page.</p><p><strong>Note: Pre-registration is required.</strong></p></td></tr></tbody></table>

***

* **Response:**

{% tabs %}
{% tab title="100" %}
```
{
    "CodeResult": "100",
    "ErrorMessage": "success",
    "TotalPrice": 660.0000,
    "TotalReceiver": 1
}
```

**Valid request.**
{% endtab %}

{% tab title="101" %}
```
{
    "CodeResult": "101",
    "ErrorMessage": "Authorize Failed"
}
```

**Invalid credential.**
{% endtab %}
{% endtabs %}

* **Response body:**

| Paramter      | Type   | Description                                  |
| ------------- | ------ | -------------------------------------------- |
|  CodeResult   | string | Response code.                               |
|  ErrorMessage | string | The error message if the request is invalid. |
| TotalPrice    | string | The cost of submit.                          |
| TotalReceiver | string | Total valid receivers in submit.             |

* _<mark style="color:yellow;">**The detail of error code can refer at**</mark>_ [**Table of error codes**](../table-of-error-codes.md) **.**
* _<mark style="color:yellow;">**Get the  sample of code for programing languagues to use in Postman refer at**</mark>_ [**Link  of code samples**](https://samplefordevelopers.esms.vn/#850974b9-12cf-46f5-946c-e8e15aa3585b)**.**
