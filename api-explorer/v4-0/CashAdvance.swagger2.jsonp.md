<!-- Generator: Widdershins v4.0.1 -->

<h1 id="cash-advance-api-documentation">Cash Advance API Documentation v1.0</h1>

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

Base URLs:

* <a href="//us.api.concursolutions.com/cashadvance/v4">//us.api.concursolutions.com/cashadvance/v4</a>

<h1 id="cash-advance-api-documentation-cash-advance-api">Cash Advance API</h1>

## post__cashadvances

> Code samples

```shell
# You can also use wget
curl -X POST /us.api.concursolutions.com/cashadvance/v4/cashadvances \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'concur-correlationid: string'

```

```http
POST /us.api.concursolutions.com/cashadvance/v4/cashadvances HTTP/1.1

Content-Type: application/json
Accept: application/json
concur-correlationid: string

```

```javascript
const inputBody = '{
  "accountCode": "string",
  "amountRequested": {
    "amount": 0,
    "currency": "string"
  },
  "comment": "string",
  "name": "string",
  "purpose": "string",
  "userId": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'concur-correlationid':'string'
};

fetch('/us.api.concursolutions.com/cashadvance/v4/cashadvances',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'concur-correlationid' => 'string'
}

result = RestClient.post '/us.api.concursolutions.com/cashadvance/v4/cashadvances',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'concur-correlationid': 'string'
}

r = requests.post('/us.api.concursolutions.com/cashadvance/v4/cashadvances', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'concur-correlationid' => 'string',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/us.api.concursolutions.com/cashadvance/v4/cashadvances', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/us.api.concursolutions.com/cashadvance/v4/cashadvances");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "concur-correlationid": []string{"string"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/us.api.concursolutions.com/cashadvance/v4/cashadvances", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /cashadvances`

*Create a Cash Advance*

> Body parameter

```json
{
  "accountCode": "string",
  "amountRequested": {
    "amount": 0,
    "currency": "string"
  },
  "comment": "string",
  "name": "string",
  "purpose": "string",
  "userId": "string"
}
```

<h3 id="post__cashadvances-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|concur-correlationid|header|string|true|The unique identifier of the consumer making the API calls|
|body|body|[CashAdvance](#schemacashadvance)|true|Cash Advance Request Data|

> Example responses

> 201 Response

```json
{
  "cashAdvanceId": "string"
}
```

<h3 id="post__cashadvances-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Created|[CreateCashAdvanceResponse](#schemacreatecashadvanceresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Invalid request body|[ObjectArrayOfErrorItems](#schemaobjectarrayoferroritems)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Invalid or nonexistent authorization HTTP header|[ObjectArrayOfErrorItems](#schemaobjectarrayoferroritems)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Permission Denied|[ObjectArrayOfErrorItems](#schemaobjectarrayoferroritems)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not found|[ObjectArrayOfErrorItems](#schemaobjectarrayoferroritems)|
|408|[Request Timeout](https://tools.ietf.org/html/rfc7231#section-6.5.7)|Timed out|[ObjectArrayOfErrorItems](#schemaobjectarrayoferroritems)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal server error|[ObjectArrayOfErrorItems](#schemaobjectarrayoferroritems)|
|503|[Service Unavailable](https://tools.ietf.org/html/rfc7231#section-6.6.4)|The service is currently unavailable|[ObjectArrayOfErrorItems](#schemaobjectarrayoferroritems)|

<aside class="success">
This operation does not require authentication
</aside>

## get__cashadvances_{cashadvanceId}

> Code samples

```shell
# You can also use wget
curl -X GET /us.api.concursolutions.com/cashadvance/v4/cashadvances/{cashadvanceId} \
  -H 'Accept: application/json' \
  -H 'concur-correlationid: string'

```

```http
GET /us.api.concursolutions.com/cashadvance/v4/cashadvances/{cashadvanceId} HTTP/1.1

Accept: application/json
concur-correlationid: string

```

```javascript

const headers = {
  'Accept':'application/json',
  'concur-correlationid':'string'
};

fetch('/us.api.concursolutions.com/cashadvance/v4/cashadvances/{cashadvanceId}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'concur-correlationid' => 'string'
}

result = RestClient.get '/us.api.concursolutions.com/cashadvance/v4/cashadvances/{cashadvanceId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'concur-correlationid': 'string'
}

r = requests.get('/us.api.concursolutions.com/cashadvance/v4/cashadvances/{cashadvanceId}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'concur-correlationid' => 'string',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/us.api.concursolutions.com/cashadvance/v4/cashadvances/{cashadvanceId}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/us.api.concursolutions.com/cashadvance/v4/cashadvances/{cashadvanceId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "concur-correlationid": []string{"string"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/us.api.concursolutions.com/cashadvance/v4/cashadvances/{cashadvanceId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /cashadvances/{cashadvanceId}`

*Get Details of a Cash Advance*

<h3 id="get__cashadvances_{cashadvanceid}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|cashadvanceId|path|string|true|Unique identifier for cash advance|
|concur-correlationid|header|string|true|The unique identifier of the consumer making the API calls|

> Example responses

> 200 Response

```json
{
  "paymentType": {
    "description": "string",
    "paymentCode": "string"
  },
  "exchangeRate": {
    "operation": "string",
    "value": "string"
  },
  "amountRequested": {
    "amount": 0,
    "currency": "string",
    "value": "string"
  },
  "availableBalance": {
    "amount": "string",
    "currency": "string"
  },
  "approvalStatus": {
    "code": "string",
    "name": "string"
  },
  "cashAdvanceId": "string",
  "requestDate": "string",
  "name": "string",
  "purpose": "string",
  "issuedDate": "string",
  "accountCode": "string",
  "comment": "string",
  "lastModifiedDate": "string",
  "hasReceipts": true,
  "reimbursementCurrency": "string"
}
```

<h3 id="get__cashadvances_{cashadvanceid}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[CashAdvanceData](#schemacashadvancedata)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Param: invalid Cash Advance Id.|[ObjectArrayOfErrorItems](#schemaobjectarrayoferroritems)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Invalid or nonexistent authorization HTTP header|[ObjectArrayOfErrorItems](#schemaobjectarrayoferroritems)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Permission Denied|[ObjectArrayOfErrorItems](#schemaobjectarrayoferroritems)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not found|[ObjectArrayOfErrorItems](#schemaobjectarrayoferroritems)|
|408|[Request Timeout](https://tools.ietf.org/html/rfc7231#section-6.5.7)|Timed out|[ObjectArrayOfErrorItems](#schemaobjectarrayoferroritems)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|An unexpected error has prevented the operation|[ObjectArrayOfErrorItems](#schemaobjectarrayoferroritems)|
|503|[Service Unavailable](https://tools.ietf.org/html/rfc7231#section-6.6.4)|The service is currently unavailable|[ObjectArrayOfErrorItems](#schemaobjectarrayoferroritems)|

<aside class="success">
This operation does not require authentication
</aside>

## post__cashadvances_{cashadvanceId}_issue

> Code samples

```shell
# You can also use wget
curl -X POST /us.api.concursolutions.com/cashadvance/v4/cashadvances/{cashadvanceId}/issue \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'concur-correlationid: string'

```

```http
POST /us.api.concursolutions.com/cashadvance/v4/cashadvances/{cashadvanceId}/issue HTTP/1.1

Content-Type: application/json
Accept: application/json
concur-correlationid: string

```

```javascript
const inputBody = '{
  "accountCode": "string",
  "comment": "string",
  "exchangeRate": 0
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'concur-correlationid':'string'
};

fetch('/us.api.concursolutions.com/cashadvance/v4/cashadvances/{cashadvanceId}/issue',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'concur-correlationid' => 'string'
}

result = RestClient.post '/us.api.concursolutions.com/cashadvance/v4/cashadvances/{cashadvanceId}/issue',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'concur-correlationid': 'string'
}

r = requests.post('/us.api.concursolutions.com/cashadvance/v4/cashadvances/{cashadvanceId}/issue', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'concur-correlationid' => 'string',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/us.api.concursolutions.com/cashadvance/v4/cashadvances/{cashadvanceId}/issue', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/us.api.concursolutions.com/cashadvance/v4/cashadvances/{cashadvanceId}/issue");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "concur-correlationid": []string{"string"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/us.api.concursolutions.com/cashadvance/v4/cashadvances/{cashadvanceId}/issue", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /cashadvances/{cashadvanceId}/issue`

*Issue a Cash Advance*

> Body parameter

```json
{
  "accountCode": "string",
  "comment": "string",
  "exchangeRate": 0
}
```

<h3 id="post__cashadvances_{cashadvanceid}_issue-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|cashadvanceId|path|string|true|Unique identifier for cash advance|
|concur-correlationid|header|string|true|The unique identifier of the consumer making the API calls|
|body|body|[CashAdvanceIssueRequest](#schemacashadvanceissuerequest)|true|Cash Advance Request Data|

> Example responses

> 200 Response

```json
{
  "issuedDate": "string",
  "status": {
    "code": "string",
    "name": "string"
  }
}
```

<h3 id="post__cashadvances_{cashadvanceid}_issue-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Issued|[CashAdvanceIssueResponse](#schemacashadvanceissueresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Invalid request body|[ObjectArrayOfErrorItems](#schemaobjectarrayoferroritems)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Invalid or nonexistent authorization HTTP header|[ObjectArrayOfErrorItems](#schemaobjectarrayoferroritems)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Permission Denied|[ObjectArrayOfErrorItems](#schemaobjectarrayoferroritems)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not found|[ObjectArrayOfErrorItems](#schemaobjectarrayoferroritems)|
|408|[Request Timeout](https://tools.ietf.org/html/rfc7231#section-6.5.7)|Timed out|[ObjectArrayOfErrorItems](#schemaobjectarrayoferroritems)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal server error|[ObjectArrayOfErrorItems](#schemaobjectarrayoferroritems)|
|503|[Service Unavailable](https://tools.ietf.org/html/rfc7231#section-6.6.4)|The service is currently unavailable|[ObjectArrayOfErrorItems](#schemaobjectarrayoferroritems)|

<aside class="success">
This operation does not require authentication
</aside>

# Schemas

<h2 id="tocS_ObjectArrayOfErrorItems">ObjectArrayOfErrorItems</h2>
<!-- backwards compatibility -->
<a id="schemaobjectarrayoferroritems"></a>
<a id="schema_ObjectArrayOfErrorItems"></a>
<a id="tocSobjectarrayoferroritems"></a>
<a id="tocsobjectarrayoferroritems"></a>

```json
{
  "errors": [
    {
      "errorCode": 0,
      "errorMessage": "string"
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|errors|[ArrayOfErrorItems](#schemaarrayoferroritems)|false|none|none|

<h2 id="tocS_ArrayOfErrorItems">ArrayOfErrorItems</h2>
<!-- backwards compatibility -->
<a id="schemaarrayoferroritems"></a>
<a id="schema_ArrayOfErrorItems"></a>
<a id="tocSarrayoferroritems"></a>
<a id="tocsarrayoferroritems"></a>

```json
[
  {
    "errorCode": 0,
    "errorMessage": "string"
  }
]

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[ErrorItems](#schemaerroritems)]|false|none|none|

<h2 id="tocS_ErrorItems">ErrorItems</h2>
<!-- backwards compatibility -->
<a id="schemaerroritems"></a>
<a id="schema_ErrorItems"></a>
<a id="tocSerroritems"></a>
<a id="tocserroritems"></a>

```json
{
  "errorCode": 0,
  "errorMessage": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|errorCode|integer|false|none|none|
|errorMessage|string|false|none|none|

<h2 id="tocS_CreateCashAdvanceResponse">CreateCashAdvanceResponse</h2>
<!-- backwards compatibility -->
<a id="schemacreatecashadvanceresponse"></a>
<a id="schema_CreateCashAdvanceResponse"></a>
<a id="tocScreatecashadvanceresponse"></a>
<a id="tocscreatecashadvanceresponse"></a>

```json
{
  "cashAdvanceId": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|cashAdvanceId|string|false|none|Unique cash advance identifier|

<h2 id="tocS_CashAdvance">CashAdvance</h2>
<!-- backwards compatibility -->
<a id="schemacashadvance"></a>
<a id="schema_CashAdvance"></a>
<a id="tocScashadvance"></a>
<a id="tocscashadvance"></a>

```json
{
  "accountCode": "string",
  "amountRequested": {
    "amount": 0,
    "currency": "string"
  },
  "comment": "string",
  "name": "string",
  "purpose": "string",
  "userId": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|accountCode|string|false|none|The account code, if not provided, will be read from the employee profile configuration data|
|amountRequested|[ApprovalRequested](#schemaapprovalrequested)|false|none|none|
|comment|string|false|none|Comment while creating a cash advance|
|name|string|false|none|Cash advance name|
|purpose|string|false|none|Purpose of raising a cash advance|
|userId|string|false|none|The unique identifier of the SAP Concur user. Use Identity v4 to retrieve the userID|

<h2 id="tocS_ApprovalRequested">ApprovalRequested</h2>
<!-- backwards compatibility -->
<a id="schemaapprovalrequested"></a>
<a id="schema_ApprovalRequested"></a>
<a id="tocSapprovalrequested"></a>
<a id="tocsapprovalrequested"></a>

```json
{
  "amount": 0,
  "currency": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|amount|number|false|none|Amount Requested as Cash Advance|
|currency|string|false|none|The 3-letter ISO 4217 currency code|

<h2 id="tocS_CashAdvanceData">CashAdvanceData</h2>
<!-- backwards compatibility -->
<a id="schemacashadvancedata"></a>
<a id="schema_CashAdvanceData"></a>
<a id="tocScashadvancedata"></a>
<a id="tocscashadvancedata"></a>

```json
{
  "paymentType": {
    "description": "string",
    "paymentCode": "string"
  },
  "exchangeRate": {
    "operation": "string",
    "value": "string"
  },
  "amountRequested": {
    "amount": 0,
    "currency": "string",
    "value": "string"
  },
  "availableBalance": {
    "amount": "string",
    "currency": "string"
  },
  "approvalStatus": {
    "code": "string",
    "name": "string"
  },
  "cashAdvanceId": "string",
  "requestDate": "string",
  "name": "string",
  "purpose": "string",
  "issuedDate": "string",
  "accountCode": "string",
  "comment": "string",
  "lastModifiedDate": "string",
  "hasReceipts": true,
  "reimbursementCurrency": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|paymentType|[PaymentType](#schemapaymenttype)|false|none|none|
|exchangeRate|[CashAdvanceExchangeRate](#schemacashadvanceexchangerate)|false|none|none|
|amountRequested|[RequestedAmount](#schemarequestedamount)|false|none|none|
|availableBalance|[AvailableBalance](#schemaavailablebalance)|false|none|none|
|approvalStatus|[Status](#schemastatus)|false|none|none|
|cashAdvanceId|string|false|none|Unique cash advance identifier|
|requestDate|string|false|none|The date the cash advance was requested|
|name|string|false|none|Cash advance name|
|purpose|string|false|none|Purpose of raising a cash advance|
|issuedDate|string|false|none|The date the cash advance was issued|
|accountCode|string|false|none|Account code linked to the employee|
|comment|string|false|none|Comment while creating a cash advance|
|lastModifiedDate|string|false|none|The date the cash advance was last modified|
|hasReceipts|boolean|false|none|If the cash advance has receipts|
|reimbursementCurrency|string|false|none|The 3-letter ISO 4217 currency code|

<h2 id="tocS_RequestedAmount">RequestedAmount</h2>
<!-- backwards compatibility -->
<a id="schemarequestedamount"></a>
<a id="schema_RequestedAmount"></a>
<a id="tocSrequestedamount"></a>
<a id="tocsrequestedamount"></a>

```json
{
  "amount": 0,
  "currency": "string",
  "value": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|amount|number|false|none|Requested cash advance amount|
|currency|string|false|none|The 3-letter ISO 4217 currency code|
|value|string|false|none|Deprecated(Use amount)|

<h2 id="tocS_Status">Status</h2>
<!-- backwards compatibility -->
<a id="schemastatus"></a>
<a id="schema_Status"></a>
<a id="tocSstatus"></a>
<a id="tocsstatus"></a>

```json
{
  "code": "string",
  "name": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|code|string|false|none|Cash Advance Status Key|
|name|string|false|none|Cash Advance Status Name|

<h2 id="tocS_AvailableBalance">AvailableBalance</h2>
<!-- backwards compatibility -->
<a id="schemaavailablebalance"></a>
<a id="schema_AvailableBalance"></a>
<a id="tocSavailablebalance"></a>
<a id="tocsavailablebalance"></a>

```json
{
  "amount": "string",
  "currency": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|amount|string|false|none|Unsubmitted Balance|
|currency|string|false|none|The 3-letter ISO 4217 currency code|

<h2 id="tocS_CashAdvanceExchangeRate">CashAdvanceExchangeRate</h2>
<!-- backwards compatibility -->
<a id="schemacashadvanceexchangerate"></a>
<a id="schema_CashAdvanceExchangeRate"></a>
<a id="tocScashadvanceexchangerate"></a>
<a id="tocscashadvanceexchangerate"></a>

```json
{
  "operation": "string",
  "value": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|operation|string|false|none|Exchange rate operation. Supported values: 'MULTIPLY'|
|value|string|false|none|Exchange rate value|

<h2 id="tocS_PaymentType">PaymentType</h2>
<!-- backwards compatibility -->
<a id="schemapaymenttype"></a>
<a id="schema_PaymentType"></a>
<a id="tocSpaymenttype"></a>
<a id="tocspaymenttype"></a>

```json
{
  "description": "string",
  "paymentCode": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|description|string|false|none|The payment method for the cash advance|
|paymentCode|string|false|none|The ID of the payment type for the cash advance|

<h2 id="tocS_CashAdvanceIssueRequest">CashAdvanceIssueRequest</h2>
<!-- backwards compatibility -->
<a id="schemacashadvanceissuerequest"></a>
<a id="schema_CashAdvanceIssueRequest"></a>
<a id="tocScashadvanceissuerequest"></a>
<a id="tocscashadvanceissuerequest"></a>

```json
{
  "accountCode": "string",
  "comment": "string",
  "exchangeRate": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|accountCode|string|false|none|Account code linked to the employee|
|comment|string|false|none|Comment while issuing a cash advance.|
|exchangeRate|number|false|none|The exchange rate that applies to the expected expense.If no exchange rate is provided system exchange rate will be considered.|

<h2 id="tocS_CashAdvanceIssueResponse">CashAdvanceIssueResponse</h2>
<!-- backwards compatibility -->
<a id="schemacashadvanceissueresponse"></a>
<a id="schema_CashAdvanceIssueResponse"></a>
<a id="tocScashadvanceissueresponse"></a>
<a id="tocscashadvanceissueresponse"></a>

```json
{
  "issuedDate": "string",
  "status": {
    "code": "string",
    "name": "string"
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|issuedDate|string|false|none|The date the cash advance was issued|
|status|[CashAdvanceStatus](#schemacashadvancestatus)|false|none|none|

<h2 id="tocS_CashAdvanceStatus">CashAdvanceStatus</h2>
<!-- backwards compatibility -->
<a id="schemacashadvancestatus"></a>
<a id="schema_CashAdvanceStatus"></a>
<a id="tocScashadvancestatus"></a>
<a id="tocscashadvancestatus"></a>

```json
{
  "code": "string",
  "name": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|code|string|false|none|Cash Advance Status Key|
|name|string|false|none|Cash advance status name|

