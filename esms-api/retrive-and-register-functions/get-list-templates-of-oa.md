# Get list templates of OA



## HTTP request

\
<mark style="color:yellow;">**`POST`**</mark> [https://rest.esms.vn/MainService.svc/json/GetTemplate/](https://rest.esms.vn/MainService.svc/json/GetTemplate/)

* **Content Type:** <mark style="color:orange;">application/json</mark>
* **Response Type:** <mark style="color:orange;">application/json</mark>

```json
curl --location 'https://rest.esms.vn/MainService.svc/json/GetTemplate/' \
--header 'Content-Type: application/json' \
--data '{
  "ApiKey": "{{ApiKey}}",
  "SecretKey": "{{SecretKey}}",
  "OAId": "{{OAId}}",
  "SmsType": "{{SmsType}}"
}'
```

* **Request body**:

<table><thead><tr><th width="159">Paramter</th><th width="126">Type</th><th width="155" data-type="checkbox">Required</th><th>Type</th></tr></thead><tbody><tr><td>ApiKey</td><td>string</td><td>true</td><td>Your API key.</td></tr><tr><td>SecretKey</td><td>string</td><td>true</td><td>Your Secret key.</td></tr><tr><td>OAId</td><td>string</td><td>true</td><td>ID of OA</td></tr><tr><td>SmsType</td><td>string</td><td>true</td><td>Type of SMS<br>24: Priority.<br>25: Normal.</td></tr></tbody></table>

***

* **Response:**

{% tabs %}
{% tab title="100" %}
```
{
    "CodeResult": "100",
    "ErrorMessage": "success",
    "ZNSTemplates": [
        {
            "TempContent": "<div class=\"group-desc\" style=\"box-sizing: border-box; -webkit-tap-highlight-color: rgba(0, 0, 0, 0); color: #131820; font-family: Muli, sans-serif; font-size: 16px;\"> <p style=\"box-sizing: border-box; -webkit-tap-highlight-color: rgba(0, 0, 0, 0); margin: 0px; padding: 0px; color: #394e60; font-size: 0.875rem; line-height: 20px;\">Mã OTP của bạn là</p> </div> <p><span class=\"otp-code\" style=\"box-sizing: border-box; -webkit-tap-highlight-color: rgba(0, 0, 0, 0); font-weight: bold; color: #131820; font-size: 1.5rem; letter-spacing: 3.75px; line-height: 24px; display: block; padding: 12px 0px; font-family: Muli, sans-serif;\">{{otp}}</span></p> <div class=\"group-desc\" style=\"box-sizing: border-box; -webkit-tap-highlight-color: rgba(0, 0, 0, 0); color: #131820; font-family: Muli, sans-serif; font-size: 16px;\"> <p style=\"box-sizing: border-box; -webkit-tap-highlight-color: rgba(0, 0, 0, 0); margin: 0px; padding: 0px; color: #394e60; font-size: 0.875rem; line-height: 20px;\">Không tiết lộ cho bất kỳ ai, Mã xác nhận sẽ có hiệu lực trong 5 phút.</p> </div>",
            "TempId": 205644,
            "TempName": "Xác nhận đăng ký dịch vụ",
            "ZNSTempDetail": [
                {
                    "Limit": 10,
                    "Param": "otp",
                    "ParamLevel": 1,
                    "RequireType": "type_text"
                }
            ]
        }
    ]
}
```

**Valid request.**
{% endtab %}

{% tab title="101" %}
```
{
    "CodeResult": "101",
    "ErrorMessage": "Authorize Failed"
}
```

**Invalid credential.**
{% endtab %}
{% endtabs %}

* **Response body**:

<table><thead><tr><th width="174">Parameter</th><th width="201">Type</th><th>Description</th></tr></thead><tbody><tr><td>TempContent</td><td>string</td><td>The content of template in html.</td></tr><tr><td>Tempid</td><td>string</td><td>ID of template.</td></tr><tr><td>TempName</td><td>string</td><td>Name of template.</td></tr><tr><td>ZNSTempDetail</td><td>Array object</td><td>Detail of template.</td></tr><tr><td>Limit</td><td>string</td><td>The length limit of parameter.</td></tr><tr><td>Param</td><td>string</td><td>Name of parameter.</td></tr><tr><td>ParamLevel</td><td>string</td><td>Parameter index.</td></tr><tr><td>RequireType</td><td>string</td><td>Data type of paramter.</td></tr></tbody></table>

* _<mark style="color:yellow;">**The detail of error code can refer at**</mark>_ [**Table of error codes**](../table-of-error-codes.md) **.**
* _<mark style="color:yellow;">**Get the  sample of code for programing languagues to use in Postman refer at**</mark>_ [**Link  of code samples**](https://samplefordevelopers.esms.vn/#850974b9-12cf-46f5-946c-e8e15aa3585b)**.**
