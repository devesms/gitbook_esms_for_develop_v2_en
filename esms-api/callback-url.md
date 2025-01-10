# Callback Url



* When the actual status of the message is available, eSMS will callback the status to the customer's hook via HTTP GET.
* The callback will be retried a maximum of 5 times.  After 5 attempts, if the customer's URL still times out, the callback will stop.\


## Sample Callback

### Sample callback for customer care messages (SMS type 2):

{% code overflow="wrap" %}
```json
curl --location -g 'https://{{yourportalreceivecallback}}?SMSID=dc712784-9c5f-4c69-b9a8-ea69d56adc9a87&SendFailed=2&SendStatus=5&SendSuccess=0&TotalPrice=0.0000&TotalReceiver=2&TotalSent=2&RequestId=&TypeId=2&telcoid=1&phonenumber=0901888484&switchsmsid='
```
{% endcode %}

### Sample callback for promo messages (SMS type 1):

{% code overflow="wrap" %}
```
curl --location -g 'https://{{yourportalreceivecallback}}?SMSID=82b0bb8aed914a0aab8deba567c9b8c2&SendFailed=0&SendStatus=5&SendSuccess=0&TotalPrice=696987.0000&TotalReceiver=169&TotalSent=169&RequestId=&TypeId=1'
```
{% endcode %}

### Sample callback for Zalo messages (ZNS)

{% code overflow="wrap" %}
```json
curl --location -g 'https://{{yourportalreceivecallback}}?SMSID=f66545d2-c7e2-4603-984e-d2238c363c8292&SendFailed=1&SendStatus=5&SendSuccess=0&TotalPrice=0.0000&TotalReceiver=1&TotalSent=0&RequestId=&TypeId=25&telcoid=2&phonenumber=0901888484&partnerids=&error_info=%22{%5C%22error%5C%22%3A-114%2C%5C%22message%5C%22%3A%5C%22User%20is%20inactive%2C%20or%20reject%20the%20message%2C%20or%20using%20an%20outdated%20Zalo%20version%2C%20or%20other%20internal%20errors%5C%22}%22&oaid=1397492183140006179&tempid=2056446'
```
{% endcode %}

### Sample callback for Viber messages

{% code overflow="wrap" %}
```json
curl --location -g 'https://{{yourportalreceivecallback}}?SMSID=849fe08c19294b02857cf91687021a50250&SendFailed=0&SendStatus=5&SendSuccess=1&TotalPrice=470.0000&TotalReceiver=1&TotalSent=1&RequestId=&TypeId=23&telcoid=2&phonenumber=0901888484'
```
{% endcode %}

### Sample callback for Consulting Messages:

{% code overflow="wrap" %}
```json
curl --location -g 'https://{{yourportalreceivecallback}}?SMSID=7d11c87a22934df390f73ec59d8defd6205&SendFailed=0&SendStatus=5&SendSuccess=1&TotalPrice=60.0000&TotalReceiver=1&TotalSent=1&RequestId=&TypeId=26&phonenumber=312158068343230&error_info=%257B%2522data%2522%3A%257B%2522message_id%2522%3A%2522e1a60e8890be9de4c4ab%2522%2C%2522user_id%2522%3A%252231215806834323092%2522%257D%2C%2522error%2522%3A0%2C%2522message%2522%3A%2522Success%2522%257D____24%2F04%2F2024%252016%3A58%3A01&oaid=4097311281936189049&partnerids=e1a60e8890be9de4c4ab'
```
{% endcode %}

### Sample callback for Transaction Messages

{% code overflow="wrap" %}
```json
curl --location -g 'https://{{yourportalreceivecallback}}?SMSID=53dbbc6e816f4159a9035a14a787e08f172&SendFailed=0&SendStatus=5&SendSuccess=1&TotalPrice=60.0000&TotalReceiver=1&TotalSent=1&RequestId=&TypeId=26&phonenumber=312158068343230&error_info=%257B%2522data%2522%3A%257B%2522message_id%2522%3A%2522f405841b5f2352790b36%2522%2C%2522user_id%2522%3A%252231215806834323092%2522%257D%2C%2522error%2522%3A0%2C%2522message%2522%3A%2522Success%2522%257D____24%2F04%2F2024%252017%3A07%3A01&oaid=4097311281936189049&partnerids=f405841b5f2352790b36'
```
{% endcode %}

### Sample callback for user information request form:

{% code overflow="wrap" %}
```json
curl --location -g 'https://{{yourportalreceivecallback}}?SMSID=53dbbc6e816f4159a9035a14a787e08f172&SendFailed=0&SendStatus=5&SendSuccess=1&TotalPrice=60.0000&TotalReceiver=1&TotalSent=1&RequestId=&TypeId=26&phonenumber=312158068343230&error_info=%257B%2522data%2522%3A%257B%2522message_id%2522%3A%2522f405841b5f2352790b36%2522%2C%2522user_id%2522%3A%252231215806834323092%2522%257D%2C%2522error%2522%3A0%2C%2522message%2522%3A%2522Success%2522%257D____24%2F04%2F2024%252017%3A07%3A01&oaid=4097311281936189049&partnerids=f405841b5f2352790b36'
```
{% endcode %}

### Sample callback for ZNS Journey:

{% code overflow="wrap" %}
```json
curl --location -g 'https://{{yourportalreceivecallback}}?SMSID=7d11c87a22934df390f73ec59d8defd6205&SendFailed=0&SendStatus=5&SendSuccess=1&TotalPrice=220.0000&TotalReceiver=1&TotalSent=1&RequestId=&TypeId=27&phonenumber=312158068343230&error_info=%257B%2522data%2522%3A%257B%2522message_id%2522%3A%2522e1a60e8890be9de4c4ab%2522%2C%2522user_id%2522%3A%252231215806834323092%2522%257D%2C%2522error%2522%3A0%2C%2522message%2522%3A%2522Success%2522%257D____24%2F04%2F2024%252016%3A58%3A01&oaid=4097311281936189049&partnerids=e1a60e8890be9derir3gfbff'
```
{% endcode %}

## Attribute structure:

<table><thead><tr><th width="189">Properties</th><th width="185">Data Type</th><th>Describe</th></tr></thead><tbody><tr><td>SMSID</td><td>string</td><td>ID of the messages</td></tr><tr><td>SendFailed</td><td>string</td><td>Number of failed messages</td></tr><tr><td>SendStatus</td><td>string</td><td>Messages status<br>1: Pending approval.<br>2: Waiting to send.<br>4: Reject.<br>5: Sent Successfully.<br>7: Sent to the telco, waiting for the report.</td></tr><tr><td>SendSuccess</td><td>string</td><td>Number of the success messages.</td></tr><tr><td>Totalprice</td><td>string</td><td>Total price</td></tr><tr><td>TotalReceiver</td><td>string</td><td>Total number of recipients</td></tr><tr><td>TotalSent</td><td>string</td><td>Total of the messages sent</td></tr><tr><td>RequestId</td><td>string</td><td>Your requestid</td></tr><tr><td>TypeId</td><td>string</td><td>Type of messages<br>1: Promo.<br>2: Customer care/ OTP.<br>23: Viber.<br>24: ZNS OTP.<br>25: Customer care ZNS messages.</td></tr><tr><td>telcoid</td><td>string</td><td>Network<br>1: Viettel, 2: Mobi, 3: Vina, 4: Vietnammobile, 5: Gtel, 6: Itel, 7: Reddi.</td></tr><tr><td>phonenumber</td><td>string</td><td>Reveiver</td></tr><tr><td>partnerids</td><td>string</td><td>Zalo msgid <strong>(Zalo messages only).</strong></td></tr><tr><td>error_info</td><td>string</td><td>Zalo error info <strong>(Zalo message only).</strong></td></tr><tr><td>oaid</td><td>string</td><td>OA ID <strong>(Zalo message only).</strong></td></tr><tr><td>tempid</td><td>string</td><td>ZNS TemplateID <strong>(Zalo message only).</strong></td></tr></tbody></table>

