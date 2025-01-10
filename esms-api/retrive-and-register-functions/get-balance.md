# Get balance

This endpoint is used to get your balance of the account.

## HTTP request

\
<mark style="color:yellow;">**`POST`**</mark> [http://rest.esms.vn/MainService.svc/json/GetBalance\_json](http://rest.esms.vn/MainService.svc/json/GetBalance_json)\


* **Content Type:** <mark style="color:orange;">application/json</mark>
* **Response Type:** <mark style="color:orange;">application/json</mark>

```json
curl --location 'http://rest.esms.vn/MainService.svc/json/GetBalance_json' \
--header 'Content-Type: application/json' \
--data '{
"ApiKey":"{{ApiKey}}",
"SecretKey":"{{SecretKey}}"
}'
```

* **Request body:**

<table><thead><tr><th width="145">Parameter</th><th width="140">Type</th><th data-type="checkbox">Require</th><th>Description</th></tr></thead><tbody><tr><td>ApiKey</td><td>string</td><td>true</td><td>Your API Key.</td></tr><tr><td>SecretKey</td><td>string</td><td>true</td><td>Your Secret Key.</td></tr></tbody></table>

***

* **Response:**

{% tabs %}
{% tab title="100" %}
```json
{
    "Balance": 36693,
    "CodeResponse": "100",
    "UserID": 9999
}
```

**Valid request.**
{% endtab %}

{% tab title="101" %}


```json
{
    "Balance": 0,
    "CodeResponse": "101",
    "ErrorMessage": "Authorize Failed"
}
```

**Invalid credentials.**
{% endtab %}
{% endtabs %}

* **Response body:**

| Parameter    | Type   | Description           |
| ------------ | ------ | --------------------- |
| Balance      | string | Your account balance. |
| CodeResponse | string | Response code.        |
| UserID       | string | The user' id at eSMS. |

* _<mark style="color:yellow;">**The detail of error code can refer at**</mark>_ [**Table of error codes**](../table-of-error-codes.md) **.**
* _<mark style="color:yellow;">**Get the  sample of code for programing languagues to use in Postman refer at**</mark>_ [**Link  of code samples**](https://samplefordevelopers.esms.vn/#850974b9-12cf-46f5-946c-e8e15aa3585b)**.**
