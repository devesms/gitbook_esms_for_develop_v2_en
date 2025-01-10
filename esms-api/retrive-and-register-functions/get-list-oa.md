# Get list OA

This endpoing is ideal for retriving the list of connected OA at ViHAT.

## HTTP request

\
<mark style="color:yellow;">**`POST`**</mark> [https://rest.esms.vn/MainService.svc/json/ZNS/GetListZOA/](https://rest.esms.vn/MainService.svc/json/ZNS/GetListZOA/)

* **Content Type:** <mark style="color:orange;">application/json</mark>
* **Response Type:** <mark style="color:orange;">application/json</mark>

```json
curl --location 'https://rest.esms.vn/MainService.svc/json/ZNS/GetListZOA/' \
--header 'Content-Type: application/json' \
--data '{
 "ApiKey":"{{ApiKey}}",
 "SecretKey":"{{SecretKey}}"
}'
```

* **Request body:**

<table><thead><tr><th width="162">Paramter</th><th width="136">Type</th><th width="143" data-type="checkbox">Required</th><th>Description</th></tr></thead><tbody><tr><td>ApiKey</td><td>string</td><td>true</td><td>Your API key.</td></tr><tr><td>SecretKey</td><td>string</td><td>true</td><td>Your Secret key.</td></tr></tbody></table>

***

* **Response:**

{% tabs %}
{% tab title="100" %}
```json
{
    "CodeResult": "100",
    "ErrorMessage": "success",
    "ZOAList": [
        {
            "OAID": "745830328927467685",
            "OAName": "Hệ thống ESMS Marketing"
        },
        {
            "OAID": "4097311281936189049",
            "OAName": "SVoucher"
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
    "ErrorMessage": "Authorize Failed."
}
```

**Invalid credential.**
{% endtab %}
{% endtabs %}

* **Body response:**

<table><thead><tr><th width="168">Paramter</th><th width="165">Type</th><th>Description</th></tr></thead><tbody><tr><td>OAID</td><td>string</td><td>Zalo OA ID is the id at Zalo Official Account of the company or organization.<br>The company need to login to the Zalo OA management page to get this value.<br><strong>Note: Pre-registration is required.</strong></td></tr><tr><td>OAName</td><td>string</td><td>The name of OA according to the Id</td></tr></tbody></table>

* _<mark style="color:yellow;">**The detail of error code can refer at**</mark>_ [**Table of error codes**](../table-of-error-codes.md) **.**
* _<mark style="color:yellow;">**Get the  sample of code for programing languagues to use in Postman refer at**</mark>_ [**Link  of code samples**](https://samplefordevelopers.esms.vn/#850974b9-12cf-46f5-946c-e8e15aa3585b)**.**
