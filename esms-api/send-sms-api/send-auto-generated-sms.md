# Send auto-generated SMS

This endpoint is ideal for sending the automatically generated OTP to the customer by brandname.

The OTP is generated randomly and handled by ViHAT.

## HTTP request

\
<mark style="color:green;">**`GET`**</mark> [https://rest.esms.vn/MainService.svc/json/SendMessageAutoGenCode\_V4\_get?Phone={Phone}\&ApiKey={ApiKey}\&SecretKey={SecretKey}\&TimeAlive={TimeAlive}\&NumCharOfCode={NumCharOfCode}\&Brandname={Brandname}\&Type=2\&message={Content}](http://rest.esms.vn/MainService.svc/json/SendMessageAutoGenCode_V4_get?Phone={Phone}\&ApiKey={ApiKey}\&SecretKey={SecretKey}\&TimeAlive={TimeAlive}\&NumCharOfCode={NumCharOfCode}\&Brandname={Brandname}\&Type=2\&message={Content})\


* **Response Type:** <mark style="color:orange;">application/json</mark>

{% code overflow="wrap" %}
```json
curl --location --globoff 'https://rest.esms.vn/MainService.svc/json/SendMessageAutoGenCode_V4_get?Phone={{Phone}}&ApiKey={{ApiKey}}&SecretKey={{SecretKey}}&TimeAlive={{TimeAlive}}&NumCharOfCode={{NumCharOfCode}}&Brandname={{Brandname}}&Type=2&message={{Content}}&IsNumber={{IsNumber}}'
```
{% endcode %}

* **Request body**

<table><thead><tr><th width="183">Parameter</th><th width="117">Type</th><th width="147" data-type="checkbox">Required</th><th>Description</th></tr></thead><tbody><tr><td>Phone</td><td>string</td><td>true</td><td>The phone number of receiver.</td></tr><tr><td>ApiKey</td><td>string</td><td>true</td><td>Your API Key.</td></tr><tr><td>SecretKey</td><td>string</td><td>true</td><td>Your Secret Key.</td></tr><tr><td>TimeAlive</td><td>string</td><td>false</td><td>The time-to-live of the OTP.<br>Unit of cal: <strong>minute</strong> <br>Min: 2<br>Max: 15<br>Do not pass this parameter, default validity is 5 minutes</td></tr><tr><td>NumCharOfCode</td><td>string</td><td>false</td><td>Number of characters in the OTP. Default is 6.</td></tr><tr><td>Brandname</td><td>string</td><td>true</td><td>The name of the sender is shown in the header of the customer's message. <br><strong>Pre-registration is required.</strong></td></tr><tr><td>Type</td><td>string</td><td>true</td><td>2: Send customer care message</td></tr><tr><td>message</td><td>string</td><td>true</td><td><br>The content of message, you shoule place the {OTP} in your content that will contain the the generated OTP.<br>Example:<br>To send the message "12345 is your code."<br>-> The content you should put is "{OTP} is your code."</td></tr><tr><td>IsNumber</td><td>string</td><td>false</td><td>0: mixed between digits and chars.<br>1: only digits.</td></tr></tbody></table>

***

* **Response:**



{% tabs %}
{% tab title="100" %}
```json
{
    "CodeResult": "100",
    "CountRegenerate": 0,
    "SMSID": "d533459ee42b2b9525ba9eabf6a8156"
}
```

**Valid request**
{% endtab %}

{% tab title="101" %}
```json
{
    "CodeResult": "101",
    "CountRegenerate": 0,
    "ErrorMessage": "Authorize Failed"
}
```

**Invalid credential.**
{% endtab %}
{% endtabs %}

* **Response body:**

| Parameter    | Type   | Description                                  |
| ------------ | ------ | -------------------------------------------- |
| CodeResult   | string | Response code.                               |
| SMSID        | string | The message id eSMS system.                  |
| ErrorMessage | string | The error message if the request is invalid. |



* _<mark style="color:yellow;">**The detail of error code can refer at**</mark>_ [**Table of error codes**](../table-of-error-codes.md) **.**
* _<mark style="color:yellow;">**Get the  sample of code for programing languagues to use in Postman refer at**</mark>_ [**Link  of code samples**](https://samplefordevelopers.esms.vn/#850974b9-12cf-46f5-946c-e8e15aa3585b)**.**
* <mark style="color:orange;">**Use API Checkcode to check the validation of OTP. See it at**</mark> [**API Checkcode**](../other-apis/check-code.md)**.**&#x20;
