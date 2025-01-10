# Get rating information of Zalo users

## HTTP request

\
<mark style="color:yellow;">**`POST`**</mark> [https://rest.esms.vn/MainService.svc/json/ZNS/GetRating/](https://rest.esms.vn/MainService.svc/json/ZNS/GetRating/)\


* **Content Type:** <mark style="color:orange;">application/json</mark>
* **Response Type:** <mark style="color:orange;">application/json</mark>

```json
curl --location 'https://rest.esms.vn/MainService.svc/json/ZNS/GetRating/' \
--header 'Content-Type: application/json' \
--data '{
    "ApiKey": "{{ApiKey}}",
    "SecretKey": "{{SecretKey}}",
    "OAID": "{{OAID}}",
    "TemplateID": "{{TemplateID}}",
    "FromTime": "{{FromTime}}",
    "ToTime": "{{ToTime}}",
    "Offset":"{{Offset}}",
    "Limit":"{{Limit}}"
}'
```

* **Request body:**

<table><thead><tr><th width="156">Paramter</th><th width="122">Type</th><th width="137" data-type="checkbox">Required</th><th>Description</th></tr></thead><tbody><tr><td>ApiKey</td><td>string</td><td>true</td><td>Your API Key.</td></tr><tr><td>SecretKey</td><td>string</td><td>true</td><td>Your Secret Key.</td></tr><tr><td>OAID</td><td>string</td><td>true</td><td><p>Zalo OA Id is the Zalo Official Account Id of the organization. It can be obtained by accessing to the Zalo administrator page.</p><p><strong>Note: Pre-registration is required.</strong></p></td></tr><tr><td>TemplateID</td><td>string</td><td>true</td><td>The ID of template for the OA that is registered and provided by eSMS at Zalo to partner.<br>Each template will have a specified structure of body.</td></tr><tr><td>FromTime</td><td>string</td><td>true</td><td>The start time of rating</td></tr><tr><td>ToTime</td><td>string</td><td>true</td><td>The end time of rating</td></tr><tr><td>Offset</td><td>string</td><td>true</td><td>The start of element index.</td></tr><tr><td>Limit</td><td>string</td><td>true</td><td>Max elements allowed to get per call.</td></tr></tbody></table>

***

* **Response:**

{% tabs %}
{% tab title="100" %}
```json
{
    "CodeResult": "100",
    "ErrorMessage": "success",
    "Data": [
        {
            "feedbacks": [
                "Nhân viên tư vấn nhiệt tình, thái độ vui vẻ, dễ thương",
                "Chính sách hỗ trợ rõ ràng, đầy đủ và dễ hiểu",
                "Chất lượng sản phẩm rất tốt",
                "Giao hàng nhanh",
                "Dịch vụ chăm sóc rất tốt"
            ],
            "msgId": "5dcf84fe1fd8bd85e4ca",
            "note": "",
            "rate": 5,
            "submitDate": "1659750276218",
            "trackingId": ""
        }
    ],
    "Total": 1
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

<table><thead><tr><th width="192">Paramter</th><th width="155">Type</th><th>Description</th></tr></thead><tbody><tr><td>feedbacks</td><td>string</td><td>Customer comment section</td></tr><tr><td>msgId</td><td>string</td><td>Message id of Zalo</td></tr><tr><td>note</td><td>string</td><td>Customer note</td></tr><tr><td>rate</td><td>string</td><td>Number of rating star.</td></tr><tr><td>submitDate</td><td>string</td><td>submitDate: time of the rating when the customer submit the rating. The value of submitDate is in the range of from_time to to_time<br><strong>Note: the value is in timestamp (millisecond).</strong></td></tr><tr><td>trackingId</td><td>string</td><td>The tracking id that client send to ViHAT.</td></tr><tr><td>Total</td><td>string</td><td>Number of rating.</td></tr></tbody></table>

* _<mark style="color:yellow;">**The detail of error code can refer at**</mark>_ [**Table of error codes**](../table-of-error-codes.md) **.**
* _<mark style="color:yellow;">**Get the  sample of code for programing languagues to use in Postman refer at**</mark>_ [**Link  of code samples**](https://samplefordevelopers.esms.vn/#850974b9-12cf-46f5-946c-e8e15aa3585b)**.**
