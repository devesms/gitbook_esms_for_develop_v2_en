# Get list registered brandnames

This endpoint is ideal for getting the list of brandnames that registered at ViHAT.

## HTTP request

\
<mark style="color:green;">**`GET`**</mark> [https://rest.esms.vn/MainService.svc/json/GetListBrandname/\{{ApiKey\}}/\{{SecretKey\}}](https://rest.esms.vn/MainService.svc/json/GetListBrandname/%7B%7BApiKey%7D%7D/%7B%7BSecretKey%7D%7D)

* **Response Type:** <mark style="color:orange;">application/json</mark>

```json
curl --location --globoff 'https://rest.esms.vn/MainService.svc/json/GetListBrandname/{{ApiKey}}/{{SecretKey}}'
```

* **Request body:**

<table><thead><tr><th>Parameter</th><th width="152">Type</th><th width="134" data-type="checkbox">Required</th><th>Description</th></tr></thead><tbody><tr><td>ApiKey</td><td>string</td><td>true</td><td>Your API key.</td></tr><tr><td>SecretKey</td><td>string</td><td>true</td><td>Your Secret key.</td></tr></tbody></table>

***

* **Response:**

{% tabs %}
{% tab title="100" %}
```json
{
    "CodeResponse": "100",
    "ListBrandName": [
        {
            "Brandname": "Baotrixemay",
            "Type": 2
        },
        {
            "Brandname": "QC_ONLINE",
            "Type": 1
        },
        {
            "Brandname": "BAT DONG SAN GIA TOT",
            "Type": 23
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

**Invalid credentials.**
{% endtab %}
{% endtabs %}

* **Response body:**

| Paramter      | Type   | Description                                                                     |
| ------------- | ------ | ------------------------------------------------------------------------------- |
|  CodeResponse | string | Response code.                                                                  |
| Brandname     | string | Name of brandname.                                                              |
| Type          | string | <p>Type of brandname:<br>1: Advertising.<br>2: Customer care.<br>23: Viber.</p> |

* _<mark style="color:yellow;">**The detail of error code can refer at**</mark>_ [**Table of error codes**](../table-of-error-codes.md) **.**
* _<mark style="color:yellow;">**Get the  sample of code for programing languagues to use in Postman refer at**</mark>_ [**Link  of code samples**](https://samplefordevelopers.esms.vn/#850974b9-12cf-46f5-946c-e8e15aa3585b)**.**
