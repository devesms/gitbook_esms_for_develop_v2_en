# Get Zalo template details

## HTTP request

\
<mark style="color:green;">**`GET`**</mark> [https://rest.esms.vn/MainService.svc/json/GetZnsTemplateInfo?TemplateId=\{{TemplateId\}}\&ApiKey=\{{ApiKey\}}\&SecretKey=\{{SecretKey\}}\&OAId=\{{OAId\}}](https://rest.esms.vn/MainService.svc/json/GetZnsTemplateInfo?TemplateId=\{{TemplateId\}}\&ApiKey=\{{ApiKey\}}\&SecretKey=\{{SecretKey\}}\&OAId=\{{OAId\}})

* **Response Type:** <mark style="color:orange;">application/json</mark>

```json
curl --location -g 'https://rest.esms.vn/MainService.svc/json/GetZnsTemplateInfo?TemplateId={{TemplateId}}&ApiKey={{ApiKey}}&SecretKey={{SecretKey}}&OAId={{OAId}}'
```

* **Request body:**

<table><thead><tr><th width="136">Parameter</th><th width="136">Type</th><th width="150" data-type="checkbox">Required</th><th>Description</th></tr></thead><tbody><tr><td>TemplateId</td><td>string</td><td>true</td><td>The ID of template for the OA that is registered and provided by eSMS at Zalo to partner.</td></tr><tr><td>ApiKey</td><td>string</td><td>true</td><td>Your API key.</td></tr><tr><td>SecretKey</td><td>string</td><td>true</td><td>Your Secret key.</td></tr><tr><td>OAId</td><td>string</td><td>true</td><td><p>Zalo OA Id is the Zalo Official Account Id of the organization. It can be obtained by accessing to the Zalo administrator page.</p><p><strong>Note: Pre-registration is required.</strong></p></td></tr></tbody></table>

***

* **Response:**

{% tabs %}
{% tab title="100" %}
```
{
    "Data": {
        "ApplyTemplateQuota": false,
        "ListParams": [
            {
                "AcceptNull": false,
                "MaxLength": 10,
                "MinLength": 0,
                "Name": "otp",
                "Require": true,
                "Type": "STRING"
            }
        ],
        "PreviewUrl": "https://zns.oa.zalo.me/znspreview/SZk01CLsjXTYpn_B4agO0g==",
        "Status": "ENABLE",
        "TemplateDailyQuota": null,
        "TemplateId": 205644,
        "TemplateName": "Xác nhận đăng ký dịch vụ",
        "TemplateQuality": "UNDEFINED",
        "TemplateRemainingQuota": null,
        "TemplateTag": "OTP",
        "Timeout": 15000
    },
    "Error": 0,
    "Message": "Success"
}
```

**Valid request.**
{% endtab %}
{% endtabs %}

* **Response body:**

<table><thead><tr><th width="217">Parameter</th><th width="166">Type</th><th>Description</th></tr></thead><tbody><tr><td>ApplyTemplateQuota</td><td>string</td><td>This parameter indicates that whether the template is applied the daily quota limit or not.<br><strong>Note</strong>: The daily quota is only applied for some  special templates that are for testing and directly register to Zalo.<br>The normal template is not affected by this limit.</td></tr><tr><td>PreviewUrl</td><td>string</td><td>The link of review version of template.</td></tr><tr><td>Status</td><td>string</td><td>Status of template.</td></tr><tr><td>TemplateDailyQuota</td><td>string</td><td>The number of ZNS can be sent by the template of OA per day.<br>Note: This field is returned only once the applyTemplateQuota is true.</td></tr><tr><td>TemplateId</td><td>string</td><td>ID of template.</td></tr><tr><td>TemplateName</td><td>string</td><td>Name of template.</td></tr><tr><td>TemplateQuality</td><td>string</td><td><p>The quality of ZNS in last 48 hours of OA. The values are returned as following</p><p></p><ul><li>HIGH - Good quality.</li><li>MEDIUM - Medium quality.</li><li>LOW - Bad quality.</li><li>UNDEFINED - Not acknownledge (in case of no ZNS is sent)</li></ul></td></tr><tr><td>TemplateRemainingQuota</td><td>string</td><td>The remaining of ZNS can be sent by the OA for the day.<br>emplate of OA per day.<br><strong>Note</strong>: This field is returned only once the applyTemplateQuota is true.</td></tr><tr><td>TemplateTag</td><td>string</td><td><p></p><p>Loại nội dung của template. Các giá trị trả về:<br>The type of template content:</p><ul><li><strong>OTP</strong> – OTP</li><li><strong>IN_TRANSACTION</strong> – Confirm/Update transaction.</li><li><strong>POST_TRANSACTION</strong> – Related post-transaction support.</li><li><strong>ACCOUNT_UPDATE</strong> – Update account information.</li><li><strong>GENERAL_UPDATE</strong> – Update service information.</li><li><strong>FOLLOW_UP</strong> – Notify promotion to old customer.</li></ul></td></tr><tr><td>Timeout</td><td>string</td><td>The timeout of template.</td></tr><tr><td>AcceptNull</td><td>string</td><td>The field indicates that whether the template parameter can be empty or not</td></tr><tr><td>MaxLength</td><td>string</td><td>Maximum length of characters for the value.</td></tr><tr><td>MinLength</td><td>string</td><td>Minimun length of characters for the value.</td></tr><tr><td>Name</td><td>string</td><td>Parameter name.</td></tr><tr><td>Require</td><td>string</td><td>The obligation of field.</td></tr><tr><td>Type</td><td>string</td><td>The regular expression for validating the value.</td></tr></tbody></table>



* _<mark style="color:yellow;">**The detail of error code can refer at**</mark>_ [**Table of error codes**](../table-of-error-codes.md) **.**
* _<mark style="color:yellow;">**Get the  sample of code for programing languagues to use in Postman refer at**</mark>_ [**Link  of code samples**](https://samplefordevelopers.esms.vn/#850974b9-12cf-46f5-946c-e8e15aa3585b)**.**
