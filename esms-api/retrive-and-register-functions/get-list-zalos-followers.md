# Get list Zalo's followers

## HTTP request&#x20;

\
<mark style="color:yellow;">**`POST`**</mark> [https://rest.esms.vn/MainService.svc/json/ZNS/GetFollowers/](https://rest.esms.vn/MainService.svc/json/ZNS/GetFollowers/)\


* **Content Type:** <mark style="color:orange;">application/json</mark>
* **Response Type:** <mark style="color:orange;">application/json</mark>

```json
curl --location 'https://rest.esms.vn/MainService.svc/json/ZNS/GetFollowers/' \
--header 'Content-Type: application/json' \
--data '{
 "ApiKey":"{{ApiKey}}",
 "SecretKey":"{{SecretKey}}",
 "OAID":"{{OAID}}",
 "Offset": {{Offset}},
 "Count": {{Count}}
}'
```

* **Request body:**

<table><thead><tr><th width="143">Paramter</th><th width="129">Type</th><th width="152" data-type="checkbox">Required</th><th>Description</th></tr></thead><tbody><tr><td>ApiKey</td><td>string</td><td>true</td><td>Your API key.</td></tr><tr><td>SecretKey</td><td>string</td><td>true</td><td>Your Secret key.</td></tr><tr><td>OAID</td><td>string</td><td>true</td><td><p>Zalo OA Id is the Zalo Official Account Id of the organization. It can be obtained by accessing to the Zalo administrator page.</p><p><strong>Note: Pre-registration is required.</strong></p></td></tr><tr><td>Offset</td><td>string</td><td>true</td><td>The start of element index.</td></tr><tr><td>Limit</td><td>string</td><td>true</td><td>Max elements allowed to get per call.</td></tr></tbody></table>

***

* **Response:**

{% tabs %}
{% tab title="100" %}
```json
{
    "CodeResult": "100",
    "ErrorMessage": "success",
    "Followers": [
        {
            "User_Id": "7800378501923859642"
        },
        {
            "User_Id": "4176617840488517388"
        },
        {a
            "User_Id": "7000997455428487634"
        },
        {
            "User_Id": "5889364632581220929"
        }
    ],
    "Total": 208
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

<table><thead><tr><th width="168">Paramter</th><th width="183">Type</th><th>Description</th></tr></thead><tbody><tr><td>Followers</td><td>string</td><td>The list of user id followed the OA.</td></tr><tr><td>Total</td><td>string</td><td>Total of users followed OA.</td></tr></tbody></table>

* _<mark style="color:yellow;">**The detail of error code can refer at**</mark>_ [**Table of error codes**](../table-of-error-codes.md) **.**
* _<mark style="color:yellow;">**Get the  sample of code for programing languagues to use in Postman refer at**</mark>_ [**Link  of code samples**](https://samplefordevelopers.esms.vn/#850974b9-12cf-46f5-946c-e8e15aa3585b)**.**
