# Registering SMS template

This endpoint is used for registering the SMS template.

## HTTP request

\
<mark style="color:yellow;">**`POST`**</mark> [https://rest.esms.vn/MainService.svc/json/SubServicePreviewJson/](https://rest.esms.vn/MainService.svc/json/SubServicePreviewJson/)\


* **Content Type:** <mark style="color:orange;">application/json</mark>
* **Response Type:** <mark style="color:orange;">application/json</mark>

```json
curl --location 'https://rest.esms.vn/MainService.svc/json/SubServicePreviewJson/' \
--header 'Content-Type: application/json' \
--data '{
    "ApiKey": "{{ApiKey}}",
    "AssetsUrl": "{{AssetsUrl}}",
    "Brandname": "{{Brandname}}",
    "CallbackUrl": "{{CallbackUrl}}",
    "Content": "{{Content}}",
    "IsUnicode": "{{IsUnicode}}",
    "CustomerEmail": "{{CustomerEmail}}",
    "CustomerName": "{{CustomerName}}",
    "CustomerPhone": "{{CustomerPhone}}",
    "SecretKey": "{{SecretKey}}",
    "ServiceType": 2,
    "SmsType": {{SmsType}}
}'
```

* **Request body:**

<table><thead><tr><th width="167">Paramter</th><th width="126">Type</th><th width="134" data-type="checkbox">Required</th><th>Description</th></tr></thead><tbody><tr><td>ApiKey</td><td>string</td><td>true</td><td>Your API key.</td></tr><tr><td>SecretKey</td><td>string</td><td>true</td><td>Your Secret key.</td></tr><tr><td>Content</td><td>string</td><td>true</td><td>The content of template.</td></tr><tr><td>AssetsUrl</td><td>string</td><td>false</td><td>The URL download of the document that used for registration.</td></tr><tr><td>Brandname</td><td>string</td><td>true</td><td>The brandname that the template is registered for.<br>Note: Brandname must be registered before calling this request.</td></tr><tr><td>IsUnicode</td><td>string</td><td>false</td><td>Template charset<br>1. Unicode<br>0. Non-unicode</td></tr><tr><td>CustomerEmail</td><td>string</td><td>false</td><td>The email of customer end that request the registration.</td></tr><tr><td>CustomerName</td><td>string</td><td>false</td><td>The name of customer end that request the registration.</td></tr><tr><td>CustomerPhone</td><td>string</td><td>false</td><td>The phonemail of customer end that request the registration.</td></tr><tr><td>ServiceType</td><td>string</td><td>true</td><td>ServiceType = 2: Register the customer care template or fixed number.</td></tr><tr><td>SmsType</td><td>string</td><td>true</td><td>2: Customer care template.<br>8: Fixed number template.</td></tr><tr><td>CallbackUrl</td><td>string</td><td>false</td><td>The webhook URL that will be received the result of the registration process.<br>0: Failed<br>1: eSMS is received the submit<br>2: The template is registered successfully</td></tr></tbody></table>

***

* **Response:**

{% tabs %}
{% tab title="100" %}
```json
{
    "CodeResult": "100",
    "ErrorMessage": "ViHAT is moderating your template",
    "ServicePreviewId": 52353
}
```

**Valid request.**
{% endtab %}
{% endtabs %}

* **Response body:**

<table><thead><tr><th width="204">Paramter</th><th width="166">Type</th><th>Description</th></tr></thead><tbody><tr><td>CodeResult</td><td>string</td><td>Response code.</td></tr><tr><td>ErrorMessage</td><td>string</td><td>The message error in case of invalid request.</td></tr><tr><td>ServicepreviewId</td><td>string</td><td>ID of template</td></tr></tbody></table>

* _<mark style="color:yellow;">**The detail of error code can refer at**</mark>_ [**Table of error codes**](../table-of-error-codes.md) **.**
* _<mark style="color:yellow;">**Get the  sample of code for programing languagues to use in Postman refer at**</mark>_ [**Link  of code samples**](https://samplefordevelopers.esms.vn/#850974b9-12cf-46f5-946c-e8e15aa3585b)**.**
