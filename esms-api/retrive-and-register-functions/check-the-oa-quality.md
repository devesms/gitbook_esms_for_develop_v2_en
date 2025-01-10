# Check the OA quality

## HTTP request

\
<mark style="color:yellow;">**`POST`**</mark> [https://rest.esms.vn/MainService.svc/json/ZNS/GetQuality/](https://rest.esms.vn/MainService.svc/json/ZNS/GetQuality/)\


* **Content Type:** <mark style="color:orange;">application/json</mark>
* **Response Type:** <mark style="color:orange;">application/json</mark>

```json
curl --location 'https://rest.esms.vn/MainService.svc/json/ZNS/GetQuality/' \
--header 'Content-Type: application/json' \
--data '{
 "ApiKey": "{{ApiKey}}",
 "SecretKey": "{{SecretKey}}",
 "OAID": "{{OAID}}"
}'
```

* **Request body:**

<table><thead><tr><th width="142">Parameter</th><th width="133">Type</th><th width="148" data-type="checkbox">Required</th><th>Description</th></tr></thead><tbody><tr><td>ApiKey</td><td>string</td><td>true</td><td>Your API key.</td></tr><tr><td>SecretKey</td><td>string</td><td>true</td><td>Your Secret key.</td></tr><tr><td>OAID</td><td>string</td><td>true</td><td><p>Zalo OA Id is the Zalo Official Account Id of the organization. It can be obtained by accessing to the Zalo administrator page.</p><p><strong>Note: Pre-registration is required.</strong></p></td></tr></tbody></table>

***

* **Response:**

{% tabs %}
{% tab title="100" %}
```json
{
    "CodeResult": "100",
    "ErrorMessage": "success",
    "Oa7dayQuality": "HIGH",
    "OaCurrentQuality": "MEDIUM"
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

**Invalid credential.**
{% endtab %}
{% endtabs %}

* **Response body:**

<table><thead><tr><th width="183">Parameter</th><th width="159">Type</th><th>Description</th></tr></thead><tbody><tr><td>Oa7dayQuality</td><td>string</td><td><p>The quality of ZNS message in last 7 days of OA. The values is returned as following</p><p></p><ul><li>HIGH - Good quality.</li><li>MEDIUM - Medium quality.</li><li>LOW - Bad quality.</li><li>UNDEFINED - Not acknownledge (in case of no ZNS is sent)</li></ul></td></tr><tr><td>OaCurrentQuality</td><td>string</td><td><p>The quality of ZNS in last 48 hours of OA. The values are returned as following</p><p></p><ul><li>HIGH - Good quality.</li><li>MEDIUM - Medium quality.</li><li>LOW - Bad quality.</li><li>UNDEFINED - Not acknownledge (in case of no ZNS is sent)</li></ul></td></tr></tbody></table>

* _<mark style="color:yellow;">**The detail of error code can refer at**</mark>_ [**Table of error codes**](../table-of-error-codes.md) **.**
* _<mark style="color:yellow;">**Get the  sample of code for programing languagues to use in Postman refer at**</mark>_ [**Link  of code samples**](https://samplefordevelopers.esms.vn/#850974b9-12cf-46f5-946c-e8e15aa3585b)**.**
