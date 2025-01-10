# Registering the Zalo template

This endpoint is ideal for registering the Zalo template for OA.

## HTTP request

\
<mark style="color:yellow;">**`POST`**</mark> [https://rest.esms.vn/MainService.svc/json/RegisZNSTemplateJson/](https://rest.esms.vn/MainService.svc/json/RegisZNSTemplateJson/)\


* **Content Type:** <mark style="color:orange;">application/json</mark>
* **Response Type:** <mark style="color:orange;">application/json</mark>



```json
curl --location 'https://rest.esms.vn/MainService.svc/json/RegisZNSTemplateJson/' \
--header 'Content-Type: application/json' \
--data '{
    "ApiKey":"{{ApiKey}}",
    "SecretKey":"{{SecretKey}}",
    "Content":"{{Content}}",
    "ImageUrl":"{{ImageUrl}}",
    "CTA1":"{{CTA1}}",
    "CTA2":"{{CTA2}}",
    "OAID":"{{OAID}}",
    "SmsType":"{{SmsType}}",
    "CallbackUrl":"{{CallbackUrl}}"
}'
```

* **Request body:**

<table><thead><tr><th width="163">Paramter</th><th width="130">Type</th><th width="148" data-type="checkbox">Require</th><th>Description</th></tr></thead><tbody><tr><td>ApiKey</td><td>string</td><td>true</td><td>Your API key.</td></tr><tr><td>SecretKey</td><td>string</td><td>true</td><td>Your Secret key.</td></tr><tr><td>Content</td><td>string</td><td>true</td><td>The content of template.</td></tr><tr><td>ImageURL</td><td>string</td><td>true</td><td>The image URL of OA<br>Accept: .png (400x69)<br>Note: The background color must be white or black.</td></tr><tr><td>CTA 1</td><td>string</td><td>false</td><td>First CTA URL.</td></tr><tr><td>CTA 2</td><td>string</td><td>false</td><td>Second CTA URL.</td></tr><tr><td>OAID</td><td>string</td><td>true</td><td><p>Zalo OA Id is the Zalo Official Account Id of the organization. It can be obtained by accessing to the Zalo administrator page.</p><p><strong>Note: Pre-registration is required.</strong></p></td></tr><tr><td>SmsType</td><td>string</td><td>true</td><td>24: priority template<br>25: normal template</td></tr><tr><td>CallbackUrl</td><td>string</td><td>false</td><td>The webhook URL that will be received the result of the registration process.<br>0: Failed<br>1: eSMS is received the submit<br>2: The template is registered successfully</td></tr></tbody></table>

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

<table><thead><tr><th width="205">Paramter</th><th width="160">Type</th><th>Description</th></tr></thead><tbody><tr><td>CodeResult</td><td>string</td><td>Response code</td></tr><tr><td>ErrorMessage</td><td>string</td><td>The message error in case of invalid request.</td></tr><tr><td>ServicepreviewId</td><td>string</td><td>ID of template</td></tr></tbody></table>

* _<mark style="color:yellow;">**Thông tin chi tiết mã lỗi xem ở bảng:**</mark>_ [**Mã lỗi**](../table-of-error-codes.md) **.**
* _<mark style="color:yellow;">**Lấy code mẫu các ngôn ngữ trên Postman:**</mark>_ [**Link code mẫu**](https://samplefordevelopers.esms.vn/#f25701ff-8ce7-4c5d-bca6-c7eafd158977)**.**
