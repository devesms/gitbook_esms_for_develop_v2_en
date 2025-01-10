# Summary your advertising submit

This endpoint is ideal for getting the overview of your advertising submit.

The response will include the total cost of the submit as well as showing the invalid parameters that will help you re-compose the submit before sending to ViHAT.

## HTTP request&#x20;

\
<mark style="color:yellow;">**`POST`**</mark> [https://rest.esms.vn/MainService.svc/json/SummaryMultipleSMSBrandname/](https://rest.esms.vn/MainService.svc/json/SummaryMultipleSMSBrandname/)

* **Content Type:** <mark style="color:orange;">text/plain</mark>
* **Response Type:** <mark style="color:orange;">application/json</mark>

```
curl --location 'https://rest.esms.vn/MainService.svc/json/SummaryMultipleSMSBrandname/' \
--header 'Content-Type: text/plain' \
--data '<RQST>
<APIKEY>{{APIKEY}}</APIKEY>
<SECRETKEY>{{SECRETKEY}}</SECRETKEY>
<CONTENT>{{CONTENT}}</CONTENT>
<SMSTYPE>1</SMSTYPE>
<BRANDNAME>{{BRANDNAME}}</BRANDNAME>
<CONTACTS>
<CUSTOMER><PHONE>{{PHONE}}</PHONE></CUSTOMER>
<CUSTOMER><PHONE>{{PHONE}}</PHONE></CUSTOMER>
<CUSTOMER><PHONE>{{PHONE}}</PHONE></CUSTOMER>
<CUSTOMER><PHONE>{{PHONE}}</PHONE></CUSTOMER>
<CUSTOMER><PHONE>{{PHONE}}</PHONE></CUSTOMER>
<CUSTOMER><PHONE>{{PHONE}}</PHONE></CUSTOMER>
</CONTACTS>
</RQST>'
```

* **Request body:**

<table><thead><tr><th width="187">Paramter</th><th width="146">Type</th><th width="137" data-type="checkbox">Required</th><th>Description</th></tr></thead><tbody><tr><td>APIKEY</td><td>string</td><td>true</td><td>Your API Key.</td></tr><tr><td>SECRETKEY</td><td>string</td><td>true</td><td>Your Secret Key.</td></tr><tr><td>CONTENT</td><td>string</td><td>true</td><td>The content of message.</td></tr><tr><td>SMSTYPE</td><td>string</td><td>true</td><td>Message type:<br>1: Advertising.</td></tr><tr><td>BRANDNAME</td><td>string</td><td>true</td><td>Advertising brandname.</td></tr><tr><td>PHONE</td><td>string</td><td>true</td><td>The phone number. </td></tr></tbody></table>

***

* **Response:**

{% tabs %}
{% tab title="100" %}
```json
{
    "CodeResult": "100",
    "ErrorMessage": "success",
    "TotalPrice": 1691300.0000,
    "TotalReceiver": 2997
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
