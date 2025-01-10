# Purchase OA package

This endpoint is used for purchase the OA package.

## HTTP request

\
<mark style="color:yellow;">**`POST`**</mark> [https://rest.esms.vn/MainService.svc/json/RegisOAPackageJson/](https://rest.esms.vn/MainService.svc/json/RegisOAPackageJson/)\


* **Content Type:** <mark style="color:orange;">application/json</mark>
* **Response Type:** <mark style="color:orange;">application/json</mark>

```json
curl --location 'https://rest.esms.vn/MainService.svc/json/RegisOAPackageJson/' \
--header 'Content-Type: application/json' \
--data '{
    "ApiKey":"{{ApiKey}}",
    "SecretKey":"{{SecretKey}}",
    "Dateactive":"{{Dateactive}}",
    "Duaration":"{{Duaration}}",
    "OAID":"{{OAID}}",
    "Package":{{Package}}
}'
```

* **Request body:**

<table><thead><tr><th width="157">Paramter</th><th width="129">Type</th><th width="154" data-type="checkbox">Required</th><th>Description</th></tr></thead><tbody><tr><td>ApiKey</td><td>string</td><td>true</td><td>Your API Key.</td></tr><tr><td>SecretKey</td><td>string</td><td>true</td><td>Your Secret Key.</td></tr><tr><td>Dateactive</td><td>string</td><td>true</td><td>The active date of OA.<br>Format: yyyy-MM-dd</td></tr><tr><td>Duaration</td><td>string</td><td>true</td><td>The duration of OA package</td></tr><tr><td>OAID</td><td>string</td><td>true</td><td><p>Zalo OA Id is the Zalo Official Account Id of the organization. It can be obtained by accessing to the Zalo administrator page.</p><p><strong>Note: Pre-registration is required.</strong></p></td></tr><tr><td>Package</td><td>string</td><td>true</td><td>List of OA packages.<br>- 1: Trial<br>- 2: Advanced<br>- 3: Premium</td></tr></tbody></table>

***

* **Response:**

{% tabs %}
{% tab title="100" %}
```
{
    "CodeResult": "100",
    "ErrorMessage": "ViHAT is censoring trademark ownership",
    "ServicePreviewId": 52330
}
```

**Valid request.**
{% endtab %}
{% endtabs %}

* **Response body:**

<table><thead><tr><th>Parameter</th><th width="194">Type</th><th>Description</th></tr></thead><tbody><tr><td>CodeResult</td><td>string</td><td>Response code.</td></tr><tr><td>ErrorMessage</td><td>string</td><td>The message error in case of invalid request.</td></tr><tr><td>ServicepreviewId</td><td>string</td><td>eSMS registration ID of OA.</td></tr></tbody></table>

* _<mark style="color:yellow;">**The detail of error code can refer at**</mark>_ [**Table of error codes**](../table-of-error-codes.md) **.**
* _<mark style="color:yellow;">**Get the  sample of code for programing languagues to use in Postman refer at**</mark>_ [**Link  of code samples**](https://samplefordevelopers.esms.vn/#850974b9-12cf-46f5-946c-e8e15aa3585b)**.**
