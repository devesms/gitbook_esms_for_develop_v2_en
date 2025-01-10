# Send customer care message using POST X-Form

## HTTP request

\
<mark style="color:yellow;">**POST**</mark> [https://rest.esms.vn/MainService.svc/json/SendMultipleMessage\_V4\_post/](https://rest.esms.vn/MainService.svc/json/SendMultipleMessage_V4_post/)

* **Content Type:** <mark style="color:orange;">application/x-www-form-urlencoded</mark>
* **Response Type:** <mark style="color:orange;">application/json</mark>

```
curl --location 'https://rest.esms.vn/MainService.svc/json/SendMultipleMessage_V4_post/' \
--header 'Content-Type: application/x-www-form-urlencoded' \
--data-urlencode 'Phone={{Phone}}' \
--data-urlencode 'Content={{Content}}' \
--data-urlencode 'Apikey={{ApiKey}}' \
--data-urlencode 'SecretKey={{SecretKey}}' \
--data-urlencode 'SmsType=2' \
--data-urlencode 'Brandname={{Brandname}}'
```

* **Request body:**

<table><thead><tr><th width="165">Parameters</th><th width="158">Type</th><th width="137" data-type="checkbox">Required</th><th>Description</th></tr></thead><tbody><tr><td>Phone</td><td>string</td><td>true</td><td>The phone number of receiver.</td></tr><tr><td>Content</td><td>string</td><td>true</td><td>The content of message.</td></tr><tr><td>ApiKey</td><td>string</td><td>true</td><td>Your API Key.</td></tr><tr><td>SecretKey</td><td>string</td><td>true</td><td>Your Secret Key.</td></tr><tr><td>SmsType</td><td>number</td><td>true</td><td>Message type:<br>2: Customer care message.</td></tr><tr><td>Brandname</td><td>string</td><td>true</td><td>The name of the sender is shown in the header of the customer's message. <br>Pre-registration is required.</td></tr></tbody></table>

***

* **Response:**

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
    "CodeResult": "101",
    "CountRegenerate": 0,
    "ErrorMessage": "Authorize Failed"
}
```

**Invalid credential.**
{% endtab %}

{% tab title="104" %}
```json
{
    "CodeResult": "104",
    "CountRegenerate": 0,
    "ErrorMessage": "Brand name code is not exist"
}
```

**Invalid brandname.**
{% endtab %}

{% tab title="Untitled" %}
```json
{
  "error": "Invalid request"
}
```

**Kiểm tra lại thông tin kết nối hoặc liên hệ bộ phận chăm sóc khách hàng để được hỗ trợ khi gặp lỗi này.**
{% endtab %}
{% endtabs %}

* **Response body:**

| Parameter    | Type   | Description                                  |
| ------------ | ------ | -------------------------------------------- |
| CodeResult   | string | Response code.                               |
| SMSID        | string | The message id eSMS system.                  |
| ErrorMessage | string | The error message if the request is invalid. |

* _<mark style="color:yellow;">**The detail of error code can refer at**</mark>_ [**Table of error codes**](../table-of-error-codes.md) **.**
* _<mark style="color:yellow;">**Get the  sample of code for programing languagues to use in Postman refer at**</mark>_ [**Link  of code samples**](https://samplefordevelopers.esms.vn/#850974b9-12cf-46f5-946c-e8e15aa3585b)**.**

