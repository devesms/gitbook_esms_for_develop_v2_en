# Summary your customer care submit

This endpoint is ideal for getting the overview of your customer care submit.

The response will include the total cost of the submit as well as showing the invalid parameters that will help you re-compose the submit before sending to ViHAT.

## HTTP request

\
<mark style="color:green;">**`GET`**</mark> [https://rest.esms.vn/MainService.svc/json/SummaryMultipleMessage\_V4\_get?Phone=\{{Phone\}}\&Content=\{{Content\}}\&ApiKey=\{{ApiKey\}}\&SecretKey=\{{SecretKey\}}\&SmsType=2\&BrandName=\{{BrandName\}}](https://rest.esms.vn/MainService.svc/json/SummaryMultipleMessage_V4_get?Phone=\{{Phone\}}\&Content=\{{Content\}}\&ApiKey=\{{ApiKey\}}\&SecretKey=\{{SecretKey\}}\&SmsType=2\&BrandName=\{{BrandName\}})

* **Response Type:** <mark style="color:orange;">application/json</mark>

```
curl --location --globoff 'https://rest.esms.vn/MainService.svc/json/SummaryMultipleMessage_V4_get?Phone={{Phone}}&Content={{Content}}&ApiKey={{ApiKey}}&SecretKey={{SecretKey}}&SmsType=2&BrandName={{BrandName}}'
```

* **Request body:**

<table><thead><tr><th width="184">Parameter</th><th width="137">Type</th><th width="154" data-type="checkbox">Required</th><th>Description</th></tr></thead><tbody><tr><td>ApiKey</td><td>string</td><td>true</td><td>Your API key.</td></tr><tr><td>SecretKey</td><td>string</td><td>true</td><td>Your Secret key.</td></tr><tr><td>Brandname</td><td>string</td><td>true</td><td>The name of the sender is shown in the header of the customer's message. <br><strong>Pre-registration is required.</strong></td></tr><tr><td>SmsType</td><td>string</td><td>true</td><td>Message type:<br>2: Customer care message.</td></tr><tr><td>Phone</td><td>string</td><td>true</td><td>The phone number of receiver.</td></tr><tr><td>Content</td><td>string</td><td>true</td><td>The content of message.</td></tr><tr><td>IsUnicode</td><td>string</td><td>false</td><td><p>Message charset value (<strong>default is 0</strong>):<br>1: Unicode.</p><p>0: Non-Unicode.</p></td></tr></tbody></table>

***

* **Response:**

{% tabs %}
{% tab title="100" %}
```json
{
    "CodeResult": "100",
    "ErrorMessage": "success",
    "TotalPrice": 850,
    "TotalReceiver": 1
}
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

**Invalid credential.**
{% endtab %}

{% tab title="104" %}
```
{
    "CodeResult": "104",
    "ErrorMessage": "Brand name code is not exist"
}
```

**Wrong brandname or brandname is inactive.**
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
