<!-- Generator: Widdershins v4.0.1 -->

<h1 id="exchange-rate-broker">Exchange Rate Broker v4.0</h1>

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

Rest API for Exchange Rate Broker

Base URLs:

* <a href="//us.api.concursolutions.com/">//us.api.concursolutions.com/</a>

<h1 id="exchange-rate-broker-exchange-rate-api">Exchange Rate API</h1>

Exchange Rate Controller

## uploadExchangeRateUsingPOST

<a id="opIduploadExchangeRateUsingPOST"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /us.api.concursolutions.com/exchangerate/v4/rates \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
POST /us.api.concursolutions.com/exchangerate/v4/rates HTTP/1.1

Content-Type: application/json
Accept: application/json

```

```javascript
const inputBody = '{
  "currency_sets": [
    {
      "from_crn_code": "USD",
      "rate": 1.0005,
      "start_date": "2020-01-30",
      "to_crn_code": "CNY"
    }
  ]
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'
};

fetch('/us.api.concursolutions.com/exchangerate/v4/rates',
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
  'Accept' => 'application/json'
}

result = RestClient.post '/us.api.concursolutions.com/exchangerate/v4/rates',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/us.api.concursolutions.com/exchangerate/v4/rates', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/us.api.concursolutions.com/exchangerate/v4/rates', array(
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
URL obj = new URL("/us.api.concursolutions.com/exchangerate/v4/rates");
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
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/us.api.concursolutions.com/exchangerate/v4/rates", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /exchangerate/v4/rates`

*Upload custom exchange rates for an entity.*

> Body parameter

```json
{
  "currency_sets": [
    {
      "from_crn_code": "USD",
      "rate": 1.0005,
      "start_date": "2020-01-30",
      "to_crn_code": "CNY"
    }
  ]
}
```

<h3 id="uploadexchangerateusingpost-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[BulkExchangeRateUploadRequest](#schemabulkexchangerateuploadrequest)|true|bulkUploadRequest|

> Example responses

> 200 Response

```json
{
  "currencySets": [
    {
      "from_crn_code": "USD",
      "rate": 1.0005,
      "start_date": "2020-01-30",
      "statusCode": 200,
      "statusMessage": "success",
      "to_crn_code": "CNY"
    }
  ],
  "message": "Requests completed successfully",
  "overallStatus": "Success"
}
```

<h3 id="uploadexchangerateusingpost-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successfully uploaded exchange rates|[BulkExchangeRateUploadResponse](#schemabulkexchangerateuploadresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Invalid request received|[ErrorMessage](#schemaerrormessage)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Access Denied|[ErrorMessage](#schemaerrormessage)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Invalid JWT. Expected a valid company JWT|[ErrorMessage](#schemaerrormessage)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Unable to find exchange rate|[ErrorMessage](#schemaerrormessage)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal server error, please contact the administrator.|[ErrorMessage](#schemaerrormessage)|
|503|[Service Unavailable](https://tools.ietf.org/html/rfc7231#section-6.6.4)|The service is unavailable either due to being offline or refusing the connection|[ErrorMessage](#schemaerrormessage)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, None
</aside>

# Schemas

<h2 id="tocS_BulkExchangeRateUploadRequest">BulkExchangeRateUploadRequest</h2>
<!-- backwards compatibility -->
<a id="schemabulkexchangerateuploadrequest"></a>
<a id="schema_BulkExchangeRateUploadRequest"></a>
<a id="tocSbulkexchangerateuploadrequest"></a>
<a id="tocsbulkexchangerateuploadrequest"></a>

```json
{
  "currency_sets": [
    {
      "from_crn_code": "USD",
      "rate": 1.0005,
      "start_date": "2020-01-30",
      "to_crn_code": "CNY"
    }
  ]
}

```

BulkExchangeRateUploadRequest

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|currency_sets|[[ExchangeRateUploadRequest](#schemaexchangerateuploadrequest)]|true|none|List of currency pairs with exchange rate, and start date|

<h2 id="tocS_BulkExchangeRateUploadResponse">BulkExchangeRateUploadResponse</h2>
<!-- backwards compatibility -->
<a id="schemabulkexchangerateuploadresponse"></a>
<a id="schema_BulkExchangeRateUploadResponse"></a>
<a id="tocSbulkexchangerateuploadresponse"></a>
<a id="tocsbulkexchangerateuploadresponse"></a>

```json
{
  "currencySets": [
    {
      "from_crn_code": "USD",
      "rate": 1.0005,
      "start_date": "2020-01-30",
      "statusCode": 200,
      "statusMessage": "success",
      "to_crn_code": "CNY"
    }
  ],
  "message": "Requests completed successfully",
  "overallStatus": "Success"
}

```

BulkExchangeRateUploadResponse

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|currencySets|[[ExchangeRateUploadResponse](#schemaexchangerateuploadresponse)]|false|none|Currency set response|
|message|string|false|none|Overall message for the response|
|overallStatus|string|false|none|Overall status of the response|

<h2 id="tocS_ErrorMessage">ErrorMessage</h2>
<!-- backwards compatibility -->
<a id="schemaerrormessage"></a>
<a id="schema_ErrorMessage"></a>
<a id="tocSerrormessage"></a>
<a id="tocserrormessage"></a>

```json
{
  "errorId": "string",
  "errorMessage": "string",
  "httpStatus": 400,
  "path": "string",
  "timestamp": "2016-10-04T00:53:25.931+0000",
  "validationErrors": [
    {
      "message": "string",
      "source": "string"
    }
  ]
}

```

ErrorMessage

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|errorId|string|false|none|The unique identifier of the error associated with the response or the error response itself|
|errorMessage|string|true|none|The detailed error message|
|httpStatus|string|true|none|The http response code and phrase for the response|
|path|string|true|none|The URI of the attempted request|
|timestamp|string(date-time)|true|none|The time when the error was captured|
|validationErrors|[[ValidationError](#schemavalidationerror)]|false|none|The validation error messages|

<h2 id="tocS_ExchangeRateUploadRequest">ExchangeRateUploadRequest</h2>
<!-- backwards compatibility -->
<a id="schemaexchangerateuploadrequest"></a>
<a id="schema_ExchangeRateUploadRequest"></a>
<a id="tocSexchangerateuploadrequest"></a>
<a id="tocsexchangerateuploadrequest"></a>

```json
{
  "from_crn_code": "USD",
  "rate": 1.0005,
  "start_date": "2020-01-30",
  "to_crn_code": "CNY"
}

```

ExchangeRateUploadRequest

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|from_crn_code|string|true|none|From currency code (ISO 4217 alphabetic code)|
|rate|number|true|none|Rate|
|start_date|string|true|none|Start date|
|to_crn_code|string|true|none|To currency code (ISO 4217 alphabetic code)|

<h2 id="tocS_ExchangeRateUploadResponse">ExchangeRateUploadResponse</h2>
<!-- backwards compatibility -->
<a id="schemaexchangerateuploadresponse"></a>
<a id="schema_ExchangeRateUploadResponse"></a>
<a id="tocSexchangerateuploadresponse"></a>
<a id="tocsexchangerateuploadresponse"></a>

```json
{
  "from_crn_code": "USD",
  "rate": 1.0005,
  "start_date": "2020-01-30",
  "statusCode": 200,
  "statusMessage": "success",
  "to_crn_code": "CNY"
}

```

ExchangeRateUploadResponse

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|from_crn_code|string|false|none|From currency code (ISO 4217 alphabetic code)|
|rate|number|false|none|Rate|
|start_date|string|false|none|Start date|
|statusCode|integer(int32)|false|none|Status Code|
|statusMessage|string|false|none|Status Message|
|to_crn_code|string|false|none|To currency code (ISO 4217 alphabetic code)|

<h2 id="tocS_ValidationError">ValidationError</h2>
<!-- backwards compatibility -->
<a id="schemavalidationerror"></a>
<a id="schema_ValidationError"></a>
<a id="tocSvalidationerror"></a>
<a id="tocsvalidationerror"></a>

```json
{
  "message": "string",
  "source": "string"
}

```

ValidationError

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|message|string|false|none|The detailed message of the validation error|
|source|string|false|none|The type of validation which failed|

