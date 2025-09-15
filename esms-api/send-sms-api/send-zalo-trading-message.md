# Send Zalo Trading message

## HTTP request

\
<mark style="color:yellow;">**`POST`**</mark> [https://rest.esms.vn/mainservice.svc/json/SendZaloFollowerMessage\_V5\_post\_json/](http://rest.esms.vn/mainservice.svc/json/SendZaloFollowerMessage_V5_post_json/)



* **Content Type:** <mark style="color:orange;">text/plain</mark>
* **Response Type:** <mark style="color:orange;">application/json</mark>

```json
curl --location 'https://rest.esms.vn/mainservice.svc/json/SendZaloFollowerMessage_V5_post_json/' \
--header 'Content-Type: text/plain' \
--data '{
    "ApiKey": "{{ApiKey}}",
    "SecretKey": "{{SecretKey}}",
    "OAID": "{{OAID}}",
    "RequestId": "96accf59-0c41-4bc7-a5c4-4a466c2e41c2", 
    "Payload": {
        "recipient": {
            "user_id": "{{user_id}}"
        },
        "message": {
            "attachment": {
                "type": "template",
                "payload": {
                    "template_type": "transaction_order",
                    "language": "VI",
                    "elements": [
                        {
                            "image_url": "https://minio.esms.vn/blogimg/agent-1/BlogImg/full_cccc34d4-3a46-4644-8613-1b226203c5d5.png",
                            "type": "banner"
                        },
                        {
                            "type": "header",
                            "content": "Trạng thái đơn hàng",
                            "align": "left"
                        },
                        {
                            "type": "text",
                            "align": "left",
                            "content": "• Cảm ơn bạn đã mua hàng tại cửa hàng.<br>• Thông tin đơn hàng của bạn như sau:"
                        },
                        {
                            "type": "table",
                            "content": [
                                {
                                    "value": "eSMS-001",
                                    "key": "Mã khách hàng"
                                },
                                {
                                    "style": "yellow",
                                    "value": "Đang giao",
                                    "key": "Trạng thái"
                                },
                                {
                                    "value": "250,000đ",
                                    "key": "Giá tiền"
                                }
                            ]
                        },
                        {
                            "type": "text",
                            "align": "center",
                            "content": "📲 Lưu ý điện thoại. Xin cảm ơn!"
                        }
                    ],
                    "buttons": [
                        {
                            "title": "Kiểm tra lộ trình",
                            "image_icon": "https://img.icons8.com/?size=100&id=kJlyCVWJrclv&format=png&color=000000",
                            "type": "oa.open.url",
                            "payload": {
                                "url": "https://esms.vn/huong-dan/huong-dan-tich-hop/huong-dan-tich-hop-api-cua-esms-vao-website"
                            }
                        },
                        {
                            "title": "Xem lại giỏ hàng",
                            "image_icon": "https://img.icons8.com/?size=100&id=S2Z1vzGMFT1v&format=png&color=000000",
                            "type": "oa.open.url",
                            "payload": {
                                "url": "https://esms.vn/huong-dan/huong-dan-su-dung"
                            }
                        },
                        {
                            "title": "Liên hệ tổng đài",
                            "image_icon": "https://img.icons8.com/?size=100&id=KKBDB20a4V6t&format=png&color=000000",
                            "type": "oa.open.phone",
                            "payload": {
                                "phone_code": "0901888484"
                            }
                        }
                    ]
                }
            }
        }
    }
}'
```

* **Body request**

<table><thead><tr><th width="158">Parameters</th><th width="120">Type</th><th width="121" data-type="checkbox">Required</th><th>Description</th></tr></thead><tbody><tr><td>ApiKey</td><td>string</td><td>true</td><td>Your API Key.</td></tr><tr><td>SecretKey</td><td>string</td><td>true</td><td>Your Secret Key</td></tr><tr><td>OAID</td><td>string</td><td>true</td><td><p>Zalo OA Id is the Zalo Official Account Id of the organization. It can be obtained by accessing to the Zalo administrator page.</p><p><strong>Note: Pre-registration is required.</strong></p></td></tr><tr><td>user_id</td><td>string</td><td>true</td><td>The identification value of user at Zalo.</td></tr><tr><td>CallbackUrl</td><td>string</td><td>false</td><td>The webhook URL that will receive the status of message after it processed to the operator. It is used for determine whether the SMS is succcessfully delivered to the receiver or failed.<br>See the sample request at <a href="https://samplefordevelopers.esms.vn/#20f85e1f-3d9e-4ff4-bc4f-8d9c9edbc88a">here</a>.<br>More details at <a href="../callback-url.md">here</a>.</td></tr><tr><td>RequestId</td><td>string</td><td>false</td><td>Partner ID passed to block duplicates and check if needed.<br>Maximum length 50 characters.<br>Each RequestId passed is valid for blocking for 24 hours.</td></tr><tr><td>template_type</td><td>string</td><td>true</td><td><p>Type of template:<br>- transaction_billing<br>- transaction_order<br>- transaction_reward<br>- transaction_contract<br>- transaction_booking<br>- transaction_membership<br>- transaction_event<br>- transaction_transaction<br>- transaction_account<br>- transaction_internal<br>- transaction_partnership<br>- transaction_education<br>- transaction_rating</p><p></p></td></tr><tr><td>language</td><td>string</td><td>false</td><td><p>Message languague values.<br>Giá trị nhận vào:</p><ul><li>language = <strong>VI</strong></li></ul><p>or</p><ul><li>language = <strong>EN</strong></li></ul><p><br>The default content of template will be transfered corresponding to the selected languague.</p></td></tr><tr><td>image_url</td><td>string</td><td>true</td><td>The image URL.</td></tr><tr><td>align</td><td>string</td><td>false</td><td><p></p><p>Align the content:</p><ul><li>left (or blank): Align to left.</li><li>center: Align to center.</li><li>right: Align to right.</li></ul></td></tr><tr><td>table</td><td>string</td><td>true</td><td><p><strong>The structure of an element in table</strong><br>{<br> "key": "key" // maxlength = 25 <br>"value": "the value of key" // maxlength = 100<br> }<br></p><p><mark style="color:red;">It is mandantory to have one of the two element below:</mark><br>VI: <br>{ <br>"key": "Mã..." // Start with "Mã", use for identify.<br>"value": "The value of key" <br>}</p><p>EN:<br> { <br>"key": "...Code..." // It is mandantory to have the string "Code" inside.<br>"value": "The value of key"<br> }<br><mark style="color:red;">Or:</mark><br>VI:</p><p> {<br> "key": "Tên khách hàng" //It is fixed with the value "Tên khách hàng",</p><p> "value": "The vlaue of key"<br> }</p><p>EN:</p><p> {<br> "key": "Customer Name" // It is fixed with value "Customer Name" ,</p><p>"value": "The value of key" <br>}<br><mark style="color:red;">Key “Trạng thái” / “Status” is the only one key that can use the "Style" paramter:</mark><br>VN: <br>{ <br>"key": "Trạng thái" //it is fixed with value "Trạng thái"<br> "value": "the value of key"<br> "style": "yellow" // Accepted values: green, blue, yellow, red, grey <br>}</p><p>EN:<br> { <br>"key": "Status" // It is fixed with value "Status"<br> "value": "the value of key" <br>"style": "yellow" // Accepted values: green, blue, yellow, red, grey<br> }</p><p><em><strong>****Note: Maximun 5 elements can be declared.</strong></em><br></p></td></tr><tr><td>button</td><td>string</td><td>false</td><td>Maximun 4 buttons can be added.</td></tr><tr><td>Sandbox</td><td>string</td><td>false</td><td>Sandbox option value (<strong>default is 0</strong>):<br>1: For testing purpose to verify the validation of the request. Message is not charged and sent to the receiver.<br>0: Message will be processed to the receiver properly.</td></tr></tbody></table>



***

* **Response**

{% tabs %}
{% tab title="100" %}
```json
{
    "CodeResult": "100",
    "CountRegenerate": 0,
    "SMSID": "d8e0f1f0702544b2acb456ca9ccfd111250"
}
```

**Valid request.**
{% endtab %}

{% tab title="101" %}
```json
{
    "CodeResult": "101",
    "CountRegenerate": 0,
    "ErrorMessage": "Authorize Failed"
}
```

**Invlid credential.**
{% endtab %}
{% endtabs %}

* **Response body**

| Parameter    | Type   | Description                                  |
| ------------ | ------ | -------------------------------------------- |
| CodeResult   | string | Response code.                               |
| SMSID        | string | The message id of eSMS system.               |
| ErrorMessage | string | The error message if the request is invalid. |

* _<mark style="color:yellow;">**The detail of error code can refer at**</mark>_ [**Table of error codes**](../table-of-error-codes.md) **.**
* _<mark style="color:yellow;">**Get the  sample of code for programing languagues to use in Postman refer at**</mark>_ [**Link  of code samples**](https://samplefordevelopers.esms.vn/#850974b9-12cf-46f5-946c-e8e15aa3585b)**.**
