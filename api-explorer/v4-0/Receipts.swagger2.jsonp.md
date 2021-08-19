<!-- Generator: Widdershins v4.0.1 -->

<h1 id="receipts">Receipts v4.0</h1>

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

Base URLs:

* <a href="https://us.api.concursolutions.com">https://us.api.concursolutions.com</a>

<h1 id="receipts-default">Default</h1>

## post__receipts_v4_status

> Code samples

```shell
# You can also use wget
curl -X POST https://us.api.concursolutions.com/receipts/v4/status \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
POST https://us.api.concursolutions.com/receipts/v4/status HTTP/1.1
Host: us.api.concursolutions.com
Content-Type: application/json
Accept: application/json

```

```javascript
const inputBody = '{
  "receiptIds": [
    "string"
  ],
  "forwardIds": [
    "string"
  ]
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'
};

fetch('https://us.api.concursolutions.com/receipts/v4/status',
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

result = RestClient.post 'https://us.api.concursolutions.com/receipts/v4/status',
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

r = requests.post('https://us.api.concursolutions.com/receipts/v4/status', headers = headers)

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
    $response = $client->request('POST','https://us.api.concursolutions.com/receipts/v4/status', array(
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
URL obj = new URL("https://us.api.concursolutions.com/receipts/v4/status");
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
    req, err := http.NewRequest("POST", "https://us.api.concursolutions.com/receipts/v4/status", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /receipts/v4/status`

*Bulk status*

Get status information for multiple receipts at once. Either receiptIds or forwardIds can be used. Maximum 50 receipts per call.

> Body parameter

```json
{
  "receiptIds": [
    "string"
  ],
  "forwardIds": [
    "string"
  ]
}
```

<h3 id="post__receipts_v4_status-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|true|Either receiptIds or forwardIds. Include only receiptIds OR forwardIds, but not both. Limitations of Swagger 2.0 mean that the oneOf directive can't be used to properly model these parameters.|
|» receiptIds|body|[string]|false|Array of up to 50 receiptIds to retrieve status for|
|» forwardIds|body|[string]|false|Array of forwardIds (max 50) associated with receipts. When using forwardIds receipts will only be retrievable if the caller uses the same auth mechanism used to post the receipt. If both a JWT and client cert were used, the JWT will take precedence|

> Example responses

> 200 Response

```json
[
  {
    "receiptId": "string",
    "responseCode": 0,
    "receiptStatus": {
      "status": "ACCEPTED",
      "digitizationStatus": "NO_PROCESSING_REQUIRED"
    },
    "receiptEventLogs": "string"
  }
]
```

<h3 id="post__receipts_v4_status-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Bulk status results|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request. Fix the body of the request before trying again.|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Callers must provide a valid JWT and/or Concur-issued X.509 client certificate|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|The caller does not have permission to perform the intended action.|None|

<h3 id="post__receipts_v4_status-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» receiptId|string|false|none|The v4 receiptId|
|» responseCode|number|false|none|The response code associated with the status entry for this individual receipt. When calling for status of multiple receipts at once, some statuses might come back with a 200, but other might fail with a different status code, such as 404. In these cases, the failed status results will include the response code and the receiptId, but no status information.|
|» receiptStatus|object|false|none|none|
|»» status|string|false|none|The overall processing status of the receipt.|
|»» digitizationStatus|string|false|none|Status of any back-end processing related to the digitization of a physical paper receipt.|
|» receiptEventLogs|string|false|none|Link to the detailed status entries for this individual receipt.|

#### Enumerated Values

|Property|Value|
|---|---|
|status|ACCEPTED|
|status|PROCESSING|
|status|PROCESSED|
|status|FAILED|
|digitizationStatus|NO_PROCESSING_REQUIRED|
|digitizationStatus|ACCEPTED|
|digitizationStatus|PROCESSING|
|digitizationStatus|PROCESSED|
|digitizationStatus|FAILED|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None
</aside>

## get__receipts_v4_{receiptId}_digitizedImage

> Code samples

```shell
# You can also use wget
curl -X GET https://us.api.concursolutions.com/receipts/v4/{receiptId}/digitizedImage

```

```http
GET https://us.api.concursolutions.com/receipts/v4/{receiptId}/digitizedImage HTTP/1.1
Host: us.api.concursolutions.com

```

```javascript

fetch('https://us.api.concursolutions.com/receipts/v4/{receiptId}/digitizedImage',
{
  method: 'GET'

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

result = RestClient.get 'https://us.api.concursolutions.com/receipts/v4/{receiptId}/digitizedImage',
  params: {
  }

p JSON.parse(result)

```

```python
import requests

r = requests.get('https://us.api.concursolutions.com/receipts/v4/{receiptId}/digitizedImage')

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','https://us.api.concursolutions.com/receipts/v4/{receiptId}/digitizedImage', array(
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
URL obj = new URL("https://us.api.concursolutions.com/receipts/v4/{receiptId}/digitizedImage");
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

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://us.api.concursolutions.com/receipts/v4/{receiptId}/digitizedImage", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /receipts/v4/{receiptId}/digitizedImage`

*Digitized image by ID*

Get a digitized receipt image. These digitized images are the result of special processing and comply with legal regulations in certain jurisdictions.

<h3 id="get__receipts_v4_{receiptid}_digitizedimage-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|receiptId|path|string|true|The ID of the receipt.|

<h3 id="get__receipts_v4_{receiptid}_digitizedimage-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|The digitized (certified) copy of the image, complete with any accompanying PDF metadata|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Callers must provide a valid JWT and/or Concur-issued X.509 client certificate|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Caller does not have the required scope, or, depending on the type of JWT, may not have permission to access receipts for this specific user or company. In rare cases, this error code might mean that special functionality is limited to certain applications.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|No v4 receipt image exists for this receiptId|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None
</aside>

## get__receipts_v4_digitizedImages

> Code samples

```shell
# You can also use wget
curl -X GET https://us.api.concursolutions.com/receipts/v4/digitizedImages

```

```http
GET https://us.api.concursolutions.com/receipts/v4/digitizedImages HTTP/1.1
Host: us.api.concursolutions.com

```

```javascript

fetch('https://us.api.concursolutions.com/receipts/v4/digitizedImages',
{
  method: 'GET'

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

result = RestClient.get 'https://us.api.concursolutions.com/receipts/v4/digitizedImages',
  params: {
  }

p JSON.parse(result)

```

```python
import requests

r = requests.get('https://us.api.concursolutions.com/receipts/v4/digitizedImages')

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','https://us.api.concursolutions.com/receipts/v4/digitizedImages', array(
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
URL obj = new URL("https://us.api.concursolutions.com/receipts/v4/digitizedImages");
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

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://us.api.concursolutions.com/receipts/v4/digitizedImages", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /receipts/v4/digitizedImages`

*Digitized image by alternate query parameters*

Get a digitized receipt image. These digitized images are the result of special processing and comply with legal regulations in certain jurisdictions. This route is an alternative method for retrieving a digitized image, and should only be used if the caller does not have access to the receiptId associated with the image.

<h3 id="get__receipts_v4_digitizedimages-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|forwardId|query|string|false|The forwardId submitted along with the original receipt POST request|

<h3 id="get__receipts_v4_digitizedimages-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|The digitized (certified) copy of the image, complete with any accompanying PDF metadata|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Callers must provide a valid JWT and/or Concur-issued X.509 client certificate|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Caller does not have the required scope, or, depending on the type of JWT, may not have permission to access receipts for this specific user or company. In rare cases, this error code might mean that special functionality is limited to certain applications.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|No v4 receipt image exists for this receiptId|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None
</aside>

## get__receipts_v4_image-only-receipts_{receiptId}

> Code samples

```shell
# You can also use wget
curl -X GET https://us.api.concursolutions.com/receipts/v4/image-only-receipts/{receiptId} \
  -H 'Accept: application/json'

```

```http
GET https://us.api.concursolutions.com/receipts/v4/image-only-receipts/{receiptId} HTTP/1.1
Host: us.api.concursolutions.com
Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('https://us.api.concursolutions.com/receipts/v4/image-only-receipts/{receiptId}',
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
  'Accept' => 'application/json'
}

result = RestClient.get 'https://us.api.concursolutions.com/receipts/v4/image-only-receipts/{receiptId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://us.api.concursolutions.com/receipts/v4/image-only-receipts/{receiptId}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','https://us.api.concursolutions.com/receipts/v4/image-only-receipts/{receiptId}', array(
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
URL obj = new URL("https://us.api.concursolutions.com/receipts/v4/image-only-receipts/{receiptId}");
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
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://us.api.concursolutions.com/receipts/v4/image-only-receipts/{receiptId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /receipts/v4/image-only-receipts/{receiptId}`

*Image-only receipt by ID*

Get an individual image-only receipt by receiptId.

<h3 id="get__receipts_v4_image-only-receipts_{receiptid}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|receiptId|path|string|true|The ID of the receipt|

> Example responses

> 200 Response

```json
{
  "modifiedAt": "string",
  "companyId": "string",
  "dateTimeReceived": "string",
  "entityId": "string",
  "digitizationData": {
    "captureMethod": "expenseItCapture",
    "hashCode": "string"
  },
  "image": "string",
  "userId": "string",
  "id": "string",
  "digitizationStatus": "NO_PROCESSING_REQUIRED",
  "forwardId": {},
  "self": "string",
  "template": "string"
}
```

<h3 id="get__receipts_v4_image-only-receipts_{receiptid}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|JSON representing a receipt and its associated metadata.|[imageOnlyReceipt](#schemaimageonlyreceipt)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Callers must provide a valid JWT and/or Concur-issued X.509 client certificate|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|The caller does not have permission to perform the intended action.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|No receipt exists with this ID|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None
</aside>

## get__receipts_v4_image-only-receipts_{receiptId}_image

> Code samples

```shell
# You can also use wget
curl -X GET https://us.api.concursolutions.com/receipts/v4/image-only-receipts/{receiptId}/image

```

```http
GET https://us.api.concursolutions.com/receipts/v4/image-only-receipts/{receiptId}/image HTTP/1.1
Host: us.api.concursolutions.com

```

```javascript

fetch('https://us.api.concursolutions.com/receipts/v4/image-only-receipts/{receiptId}/image',
{
  method: 'GET'

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

result = RestClient.get 'https://us.api.concursolutions.com/receipts/v4/image-only-receipts/{receiptId}/image',
  params: {
  }

p JSON.parse(result)

```

```python
import requests

r = requests.get('https://us.api.concursolutions.com/receipts/v4/image-only-receipts/{receiptId}/image')

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','https://us.api.concursolutions.com/receipts/v4/image-only-receipts/{receiptId}/image', array(
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
URL obj = new URL("https://us.api.concursolutions.com/receipts/v4/image-only-receipts/{receiptId}/image");
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

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://us.api.concursolutions.com/receipts/v4/image-only-receipts/{receiptId}/image", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /receipts/v4/image-only-receipts/{receiptId}/image`

*Image by ID*

Get the image file for a given receiptId

<h3 id="get__receipts_v4_image-only-receipts_{receiptid}_image-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|receiptId|path|string|true|The ID of the receipt|

<h3 id="get__receipts_v4_image-only-receipts_{receiptid}_image-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|The v4 image file associated with the receiptId. This is not the Imaging Service copy of the image but might be visually similar.|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Callers must provide a valid JWT and/or Concur-issued X.509 client certificate|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Caller does not have the required scope, or, depending on the type of JWT, may not have permission to access receipts for this specific user or company. In rare cases, this error code might mean that special functionality is limited to certain applications.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|No v4 receipt image exists for this receiptId|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None
</aside>

## get__receipts_v4_

> Code samples

```shell
# You can also use wget
curl -X GET https://us.api.concursolutions.com/receipts/v4/ \
  -H 'Accept: application/json'

```

```http
GET https://us.api.concursolutions.com/receipts/v4/ HTTP/1.1
Host: us.api.concursolutions.com
Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('https://us.api.concursolutions.com/receipts/v4/',
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
  'Accept' => 'application/json'
}

result = RestClient.get 'https://us.api.concursolutions.com/receipts/v4/',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://us.api.concursolutions.com/receipts/v4/', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','https://us.api.concursolutions.com/receipts/v4/', array(
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
URL obj = new URL("https://us.api.concursolutions.com/receipts/v4/");
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
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://us.api.concursolutions.com/receipts/v4/", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /receipts/v4/`

*Service index*

Get a list of links to all the receipts endpoints in this environment. Call this endpoint first, then use the url templates in your code to make subsequent calls.

> Example responses

> 200 Response

```json
[
  {
    "rel": "string",
    "href": "string",
    "method": "string"
  }
]
```

<h3 id="get__receipts_v4_-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|A list of Receipts API endpoints available in this environment|Inline|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Callers must provide a valid JWT and/or Concur-issued X.509 client certificate|None|

<h3 id="get__receipts_v4_-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[linkObject](#schemalinkobject)]|false|none|none|
|» rel|string|false|none|HATEOAS "relationship" to the current resource|
|» href|string|false|none|URI template for this resource|
|» method|string|false|none|HTTP method to use against this resource|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None
</aside>

## get__receipts_v4_{receiptId}

> Code samples

```shell
# You can also use wget
curl -X GET https://us.api.concursolutions.com/receipts/v4/{receiptId} \
  -H 'Accept: application/json'

```

```http
GET https://us.api.concursolutions.com/receipts/v4/{receiptId} HTTP/1.1
Host: us.api.concursolutions.com
Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('https://us.api.concursolutions.com/receipts/v4/{receiptId}',
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
  'Accept' => 'application/json'
}

result = RestClient.get 'https://us.api.concursolutions.com/receipts/v4/{receiptId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://us.api.concursolutions.com/receipts/v4/{receiptId}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','https://us.api.concursolutions.com/receipts/v4/{receiptId}', array(
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
URL obj = new URL("https://us.api.concursolutions.com/receipts/v4/{receiptId}");
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
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://us.api.concursolutions.com/receipts/v4/{receiptId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /receipts/v4/{receiptId}`

*Receipt by ID*

Get an individual receipt by receiptId.

<h3 id="get__receipts_v4_{receiptid}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|receiptId|path|string|true|The ID of the receipt|

> Example responses

> 200 Response

```json
{
  "modifiedAt": "string",
  "companyId": "string",
  "dateTimeReceived": "string",
  "entityId": "string",
  "validationSchema": "http://schema.concursolutions.com/general-receipt.schema.json",
  "receipt": {},
  "image": "string",
  "userId": "string",
  "id": "string",
  "digitizationStatus": "NO_PROCESSING_REQUIRED",
  "forwardId": {},
  "self": "string",
  "template": "string"
}
```

<h3 id="get__receipts_v4_{receiptid}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|JSON representing an E-receipt and its associated metadata.|[eReceipt](#schemaereceipt)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Callers must provide a valid JWT and/or Concur-issued X.509 client certificate|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Caller does not have the required scope, or, depending on the type of JWT, may not have permission to access receipts for this specific user or company. In rare cases, this error code might mean that special functionality is limited to certain applications.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|No receipt exists with this ID|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None
</aside>

## get__receipts_v4_{receiptId}_image

> Code samples

```shell
# You can also use wget
curl -X GET https://us.api.concursolutions.com/receipts/v4/{receiptId}/image

```

```http
GET https://us.api.concursolutions.com/receipts/v4/{receiptId}/image HTTP/1.1
Host: us.api.concursolutions.com

```

```javascript

fetch('https://us.api.concursolutions.com/receipts/v4/{receiptId}/image',
{
  method: 'GET'

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

result = RestClient.get 'https://us.api.concursolutions.com/receipts/v4/{receiptId}/image',
  params: {
  }

p JSON.parse(result)

```

```python
import requests

r = requests.get('https://us.api.concursolutions.com/receipts/v4/{receiptId}/image')

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','https://us.api.concursolutions.com/receipts/v4/{receiptId}/image', array(
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
URL obj = new URL("https://us.api.concursolutions.com/receipts/v4/{receiptId}/image");
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

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://us.api.concursolutions.com/receipts/v4/{receiptId}/image", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /receipts/v4/{receiptId}/image`

*Image by ID*

Get the image file for a given receiptId

<h3 id="get__receipts_v4_{receiptid}_image-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|receiptId|path|string|true|The ID of the receipt|

<h3 id="get__receipts_v4_{receiptid}_image-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|The v4 image file associated with the receiptId. This is not the Imaging Service copy of the image but might be visually similar.|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Callers must provide a valid JWT and/or Concur-issued X.509 client certificate|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Caller does not have the required scope, or, depending on the type of JWT, may not have permission to access receipts for this specific user or company. In rare cases, this error code might mean that special functionality is limited to certain applications.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|No v4 receipt image exists for this receiptId|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None
</aside>

## get__receipts_v4_status_{receiptId}

> Code samples

```shell
# You can also use wget
curl -X GET https://us.api.concursolutions.com/receipts/v4/status/{receiptId}

```

```http
GET https://us.api.concursolutions.com/receipts/v4/status/{receiptId} HTTP/1.1
Host: us.api.concursolutions.com

```

```javascript

fetch('https://us.api.concursolutions.com/receipts/v4/status/{receiptId}',
{
  method: 'GET'

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

result = RestClient.get 'https://us.api.concursolutions.com/receipts/v4/status/{receiptId}',
  params: {
  }

p JSON.parse(result)

```

```python
import requests

r = requests.get('https://us.api.concursolutions.com/receipts/v4/status/{receiptId}')

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','https://us.api.concursolutions.com/receipts/v4/status/{receiptId}', array(
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
URL obj = new URL("https://us.api.concursolutions.com/receipts/v4/status/{receiptId}");
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

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://us.api.concursolutions.com/receipts/v4/status/{receiptId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /receipts/v4/status/{receiptId}`

*Receipt status*

Get status information about a receipt.

<h3 id="get__receipts_v4_status_{receiptid}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|receiptId|path|string|true|The ID of the receipt|

<h3 id="get__receipts_v4_status_{receiptid}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Status information about the receipt, including logs about the back-end processing of the receipt.|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Callers must provide a valid JWT and/or Concur-issued X.509 client certificate|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Caller does not have the required scope, or, depending on the type of JWT, may not have permission to access receipts for this specific user or company. In rare cases, this error code might mean that special functionality is limited to certain applications.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|No status record exists for this receiptId|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None
</aside>

## get__receipts_v4_{receiptId}_states

> Code samples

```shell
# You can also use wget
curl -X GET https://us.api.concursolutions.com/receipts/v4/{receiptId}/states \
  -H 'Accept: application/json'

```

```http
GET https://us.api.concursolutions.com/receipts/v4/{receiptId}/states HTTP/1.1
Host: us.api.concursolutions.com
Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('https://us.api.concursolutions.com/receipts/v4/{receiptId}/states',
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
  'Accept' => 'application/json'
}

result = RestClient.get 'https://us.api.concursolutions.com/receipts/v4/{receiptId}/states',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://us.api.concursolutions.com/receipts/v4/{receiptId}/states', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','https://us.api.concursolutions.com/receipts/v4/{receiptId}/states', array(
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
URL obj = new URL("https://us.api.concursolutions.com/receipts/v4/{receiptId}/states");
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
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://us.api.concursolutions.com/receipts/v4/{receiptId}/states", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /receipts/v4/{receiptId}/states`

*Receipt by ID*

Get an individual receipt by receiptId, including state metadata. The JSON will include links that can be called to change the state of the receipt.

<h3 id="get__receipts_v4_{receiptid}_states-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|receiptId|path|string|true|The ID of the receipt|

> Example responses

> 200 Response

```json
{
  "links": [
    {
      "href": "string",
      "method": "string",
      "rel": "string"
    }
  ],
  "modifiedAt": "string",
  "companyId": "string",
  "dateTimeReceived": "string",
  "entityId": "string",
  "validationSchema": "http://schema.concursolutions.com/general-receipt.schema.json",
  "receipt": {},
  "image": "string",
  "userId": "string",
  "id": "string",
  "digitizationStatus": "NO_PROCESSING_REQUIRED",
  "forwardId": {},
  "self": "string",
  "template": "string"
}
```

<h3 id="get__receipts_v4_{receiptid}_states-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|JSON representing an E-receipt and its associated metadata.|Inline|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Callers must provide a valid JWT and/or Concur-issued X.509 client certificate|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Caller does not have the required scope, or, depending on the type of JWT, may not have permission to access receipts for this specific user or company. In rare cases, this error code might mean that special functionality is limited to certain applications.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|No receipt exists with this ID|None|

<h3 id="get__receipts_v4_{receiptid}_states-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» links|[object]|false|none|none|
|»» href|string|false|none|HATEOAS link to call to change the state of the receipt|
|»» method|string|false|none|HTTP method to use with the href|
|»» rel|string|false|none|HATEOAS relationship of the link to the current resource|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None
</aside>

## get__receipts_schemas_

> Code samples

```shell
# You can also use wget
curl -X GET https://us.api.concursolutions.com/receipts/schemas/ \
  -H 'Accept: application/json'

```

```http
GET https://us.api.concursolutions.com/receipts/schemas/ HTTP/1.1
Host: us.api.concursolutions.com
Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('https://us.api.concursolutions.com/receipts/schemas/',
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
  'Accept' => 'application/json'
}

result = RestClient.get 'https://us.api.concursolutions.com/receipts/schemas/',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://us.api.concursolutions.com/receipts/schemas/', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','https://us.api.concursolutions.com/receipts/schemas/', array(
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
URL obj = new URL("https://us.api.concursolutions.com/receipts/schemas/");
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
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://us.api.concursolutions.com/receipts/schemas/", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /receipts/schemas/`

*Schema index*

Returns objects with links to all available schemas, including the schemas used to validate E-receipts. Call the links returned from this route to retrieve individual schemas.

> Example responses

> 200 Response

```json
{
  "receiptSchemas": [
    {
      "rel": "string",
      "href": "string",
      "method": "string"
    }
  ]
}
```

<h3 id="get__receipts_schemas_-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|A list of JSON schemas|Inline|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Callers must provide a valid JWT and/or Concur-issued X.509 client certificate|None|

<h3 id="get__receipts_schemas_-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» receiptSchemas|[[linkObject](#schemalinkobject)]|true|none|none|
|»» rel|string|false|none|HATEOAS "relationship" to the current resource|
|»» href|string|false|none|URI template for this resource|
|»» method|string|false|none|HTTP method to use against this resource|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None
</aside>

## get__receipts_schemas_{schemaId}

> Code samples

```shell
# You can also use wget
curl -X GET https://us.api.concursolutions.com/receipts/schemas/{schemaId} \
  -H 'Accept: application/json'

```

```http
GET https://us.api.concursolutions.com/receipts/schemas/{schemaId} HTTP/1.1
Host: us.api.concursolutions.com
Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('https://us.api.concursolutions.com/receipts/schemas/{schemaId}',
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
  'Accept' => 'application/json'
}

result = RestClient.get 'https://us.api.concursolutions.com/receipts/schemas/{schemaId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://us.api.concursolutions.com/receipts/schemas/{schemaId}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','https://us.api.concursolutions.com/receipts/schemas/{schemaId}', array(
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
URL obj = new URL("https://us.api.concursolutions.com/receipts/schemas/{schemaId}");
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
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://us.api.concursolutions.com/receipts/schemas/{schemaId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /receipts/schemas/{schemaId}`

*Schema by ID*

Get an individual schema by schemaId. Find schemaIds by calling the schema index.

<h3 id="get__receipts_schemas_{schemaid}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|schemaId|path|string|true|The ID of the schema|

> Example responses

> 200 Response

```json
{}
```

<h3 id="get__receipts_schemas_{schemaid}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|A single JSON schema|Inline|

<h3 id="get__receipts_schemas_{schemaid}-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None
</aside>

## get__receipts_v4_{receiptId}_sdr

> Code samples

```shell
# You can also use wget
curl -X GET https://us.api.concursolutions.com/receipts/v4/{receiptId}/sdr \
  -H 'Accept: application/json'

```

```http
GET https://us.api.concursolutions.com/receipts/v4/{receiptId}/sdr HTTP/1.1
Host: us.api.concursolutions.com
Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('https://us.api.concursolutions.com/receipts/v4/{receiptId}/sdr',
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
  'Accept' => 'application/json'
}

result = RestClient.get 'https://us.api.concursolutions.com/receipts/v4/{receiptId}/sdr',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://us.api.concursolutions.com/receipts/v4/{receiptId}/sdr', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','https://us.api.concursolutions.com/receipts/v4/{receiptId}/sdr', array(
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
URL obj = new URL("https://us.api.concursolutions.com/receipts/v4/{receiptId}/sdr");
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
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://us.api.concursolutions.com/receipts/v4/{receiptId}/sdr", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /receipts/v4/{receiptId}/sdr`

*SDR*

Get the structured data record (SDR) for a receipt. This data is related to tax regulations in certain jurisdictions.

<h3 id="get__receipts_v4_{receiptid}_sdr-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|receiptId|path|string|true|The ID of the receipt|

> Example responses

> 200 Response

```json
{
  "invoiceNumber": "string",
  "invoiceType": "FA",
  "supplierName": "string",
  "supplierTaxId": "string",
  "supplierAddress": {
    "streetAddress": "string",
    "addressLocality": "string",
    "addressRegion": "string",
    "addressCountry": "st",
    "postalCode": "st"
  },
  "transactionDate": "string",
  "issueDate": "string",
  "taxes": [
    {
      "taxRate": "string",
      "taxBase": "string",
      "rateType": "reduced",
      "amount": "string"
    }
  ]
}
```

<h3 id="get__receipts_v4_{receiptid}_sdr-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|JSON representing an SDR.|[sdr](#schemasdr)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Callers must provide a valid JWT and/or Concur-issued X.509 client certificate|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Caller does not have the required scope, or, depending on the type of JWT, may not have permission to access receipts for this specific user or company. In rare cases, this error code might mean that special functionality is limited to certain applications.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|No receipt exists with this ID|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None
</aside>

## post__receipts_v4_{receiptId}_sdr

> Code samples

```shell
# You can also use wget
curl -X POST https://us.api.concursolutions.com/receipts/v4/{receiptId}/sdr \
  -H 'Content-Type: application/json' \
  -H 'link: <http://schema.concursolutions.com/spain-sdr.schema.json>;rel=describedBy'

```

```http
POST https://us.api.concursolutions.com/receipts/v4/{receiptId}/sdr HTTP/1.1
Host: us.api.concursolutions.com
Content-Type: application/json

link: <http://schema.concursolutions.com/spain-sdr.schema.json>;rel=describedBy

```

```javascript
const inputBody = '{
  "sdrData": {
    "invoiceNumber": "string",
    "invoiceType": "FA",
    "supplierName": "string",
    "supplierTaxId": "string",
    "supplierAddress": {
      "streetAddress": "string",
      "addressLocality": "string",
      "addressRegion": "string",
      "addressCountry": "st",
      "postalCode": "st"
    },
    "transactionDate": "string",
    "issueDate": "string",
    "taxes": [
      {
        "taxRate": "string",
        "taxBase": "string",
        "rateType": "reduced",
        "amount": "string"
      }
    ]
  }
}';
const headers = {
  'Content-Type':'application/json',
  'link':'<http://schema.concursolutions.com/spain-sdr.schema.json>;rel=describedBy'
};

fetch('https://us.api.concursolutions.com/receipts/v4/{receiptId}/sdr',
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
  'link' => '<http://schema.concursolutions.com/spain-sdr.schema.json>;rel=describedBy'
}

result = RestClient.post 'https://us.api.concursolutions.com/receipts/v4/{receiptId}/sdr',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'link': '<http://schema.concursolutions.com/spain-sdr.schema.json>;rel=describedBy'
}

r = requests.post('https://us.api.concursolutions.com/receipts/v4/{receiptId}/sdr', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'link' => '<http://schema.concursolutions.com/spain-sdr.schema.json>;rel=describedBy',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','https://us.api.concursolutions.com/receipts/v4/{receiptId}/sdr', array(
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
URL obj = new URL("https://us.api.concursolutions.com/receipts/v4/{receiptId}/sdr");
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
        "link": []string{"<http://schema.concursolutions.com/spain-sdr.schema.json>;rel=describedBy"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://us.api.concursolutions.com/receipts/v4/{receiptId}/sdr", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /receipts/v4/{receiptId}/sdr`

Create/update SDR data for a receipt. The receipt MUST have been successfully digitized (digitizationStatus is PROCESSED) for the request to succeed. Digitization status can be checked by calling GET /receipts/receipts/v4/status/{receiptId}

> Body parameter

```json
{
  "sdrData": {
    "invoiceNumber": "string",
    "invoiceType": "FA",
    "supplierName": "string",
    "supplierTaxId": "string",
    "supplierAddress": {
      "streetAddress": "string",
      "addressLocality": "string",
      "addressRegion": "string",
      "addressCountry": "st",
      "postalCode": "st"
    },
    "transactionDate": "string",
    "issueDate": "string",
    "taxes": [
      {
        "taxRate": "string",
        "taxBase": "string",
        "rateType": "reduced",
        "amount": "string"
      }
    ]
  }
}
```

<h3 id="post__receipts_v4_{receiptid}_sdr-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|receiptId|path|string|true|The ID of the receipt|
|link|header|string|false|A link to the SDR schema to be used to validate the incoming E-receipt data. Currently, Spain is the only locality supported for SDR.|
|body|body|object|false|JSON representation of SDR data to be updated. Nested JSON objects/arrays (supplierAddress and taxes) must also have at least one key value pair from the associated schema. For updates of a field, object, or array a non empty value must be provided. For deletion of a field, object, or array the value must be null. rateType is the only exception to this rule. To delete data associated with a tax rate, set the rateType to one of the allowed values and set any other related fields to null. Empty objects or values will not be accepted.|
|» sdrData|body|[sdr](#schemasdr)|false|none|
|»» invoiceNumber|body|string|false|none|
|»» invoiceType|body|string|false|Invoice Types for Spain. FA, FC, & OT represent a Simplified Invoice, a Full Invoice, and Other respectively|
|»» supplierName|body|string|false|none|
|»» supplierTaxId|body|string|false|none|
|»» supplierAddress|body|object|false|none|
|»»» streetAddress|body|string|false|none|
|»»» addressLocality|body|string|false|none|
|»»» addressRegion|body|string|false|none|
|»»» addressCountry|body|string|false|2-character country code|
|»»» postalCode|body|string|false|none|
|»» transactionDate|body|string|false|none|
|»» issueDate|body|string|false|none|
|»» taxes|body|[object]|false|none|
|»»» taxRate|body|string|false|String representation of Tax Rate as a decimal.|
|»»» taxBase|body|string|false|none|
|»»» rateType|body|string|true|The rate type for the tax charged. For value added tax this could be Reduced, Super Reduced, Standard, or Parking.|
|»»» amount|body|string|false|none|

#### Enumerated Values

|Parameter|Value|
|---|---|
|link|<http://schema.concursolutions.com/spain-sdr.schema.json>;rel=describedBy|
|»» invoiceType|FA|
|»» invoiceType|FC|
|»» invoiceType|OT|
|»»» rateType|reduced|
|»»» rateType|superReduced|
|»»» rateType|standard|
|»»» rateType|parking|

<h3 id="post__receipts_v4_{receiptid}_sdr-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|202|[Accepted](https://tools.ietf.org/html/rfc7231#section-6.3.3)|The SDR has been accepted for processing.|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Malformed or bad request. Fix the request parameters before trying again.|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Callers must provide a valid JWT and/or Concur-issued X.509 client certificate|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Caller does not have the required scope, or, depending on the type of JWT, may not have permission to access receipts for this specific user or company. In rare cases, this error code might mean that special functionality is limited to certain applications.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|No receipt exists with this ID|None|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Only digitized receipts are eligible for SDR|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None
</aside>

## get__receipts_v4_sdrExtracts

> Code samples

```shell
# You can also use wget
curl -X GET https://us.api.concursolutions.com/receipts/v4/sdrExtracts?company%2Did=string&fiscal%2Dperiod=string

```

```http
GET https://us.api.concursolutions.com/receipts/v4/sdrExtracts?company%2Did=string&fiscal%2Dperiod=string HTTP/1.1
Host: us.api.concursolutions.com

```

```javascript

fetch('https://us.api.concursolutions.com/receipts/v4/sdrExtracts?company%2Did=string&fiscal%2Dperiod=string',
{
  method: 'GET'

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

result = RestClient.get 'https://us.api.concursolutions.com/receipts/v4/sdrExtracts',
  params: {
  'company-id' => 'string',
'fiscal-period' => 'string'
}

p JSON.parse(result)

```

```python
import requests

r = requests.get('https://us.api.concursolutions.com/receipts/v4/sdrExtracts', params={
  'company-id': 'string',  'fiscal-period': 'string'
})

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','https://us.api.concursolutions.com/receipts/v4/sdrExtracts', array(
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
URL obj = new URL("https://us.api.concursolutions.com/receipts/v4/sdrExtracts?company%2Did=string&fiscal%2Dperiod=string");
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

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://us.api.concursolutions.com/receipts/v4/sdrExtracts", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /receipts/v4/sdrExtracts`

*SDR extract*

Get a compressed extract file containing all SDR records for a given company from a one-month fiscal period. Extracts are generated at the end of each month.

<h3 id="get__receipts_v4_sdrextracts-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|company-id|query|string|true|Company UUID|
|fiscal-period|query|string|true|One month fiscal period in the format YYYY-MM|

<h3 id="get__receipts_v4_sdrextracts-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Zip file containing all SDR records for the company during the specified fiscal period|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Callers must provide a valid JWT and/or Concur-issued X.509 client certificate|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Caller does not have the required scope, or, depending on the type of JWT, may not have permission to access receipts for this specific user or company. In rare cases, this error code might mean that special functionality is limited to certain applications.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|No extract found for this company and fiscal period. If no SDRs were generated for this company during the fiscal period, then no extract will be generated for that company.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None
</aside>

## get__receipts_v4_users_{userId}_image-only-receipts_{state}

> Code samples

```shell
# You can also use wget
curl -X GET https://us.api.concursolutions.com/receipts/v4/users/{userId}/image-only-receipts/{state} \
  -H 'Accept: application/json'

```

```http
GET https://us.api.concursolutions.com/receipts/v4/users/{userId}/image-only-receipts/{state} HTTP/1.1
Host: us.api.concursolutions.com
Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('https://us.api.concursolutions.com/receipts/v4/users/{userId}/image-only-receipts/{state}',
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
  'Accept' => 'application/json'
}

result = RestClient.get 'https://us.api.concursolutions.com/receipts/v4/users/{userId}/image-only-receipts/{state}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://us.api.concursolutions.com/receipts/v4/users/{userId}/image-only-receipts/{state}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','https://us.api.concursolutions.com/receipts/v4/users/{userId}/image-only-receipts/{state}', array(
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
URL obj = new URL("https://us.api.concursolutions.com/receipts/v4/users/{userId}/image-only-receipts/{state}");
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
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://us.api.concursolutions.com/receipts/v4/users/{userId}/image-only-receipts/{state}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /receipts/v4/users/{userId}/image-only-receipts/{state}`

*Receipts for a user by state*

Get all v4 image-only receipts for a single user with a certain state. Valid states are consumable (not attached to an expense report), consumed (attached), and discarded (deleted by the user). Maximum 50 receipts per page. If there are more results after the first page, a next page link will be provided in the results.  Calling that link will retrieve the next page of receipts.

<h3 id="get__receipts_v4_users_{userid}_image-only-receipts_{state}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|userId|path|string|true|UUID (not login ID) of the user|
|state|path|string|true|Desired state for the set of returned receipts. Valid states are consumable (not attached to an expense report), consumed (attached), and discarded (deleted by the user). Not to be confused with "status", which refers to the processing status of the receipt, not the state of the receipt within Expense.|

#### Enumerated Values

|Parameter|Value|
|---|---|
|state|consumed|
|state|consumable|
|state|discarded|

> Example responses

> 200 Response

```json
{
  "imageOnlyReceipts": [
    {
      "modifiedAt": "string",
      "companyId": "string",
      "dateTimeReceived": "string",
      "entityId": "string",
      "validationSchema": "http://schema.concursolutions.com/general-receipt.schema.json",
      "receipt": {},
      "image": "string",
      "userId": "string",
      "id": "string",
      "digitizationStatus": "NO_PROCESSING_REQUIRED",
      "forwardId": {},
      "self": "string",
      "template": "string"
    }
  ],
  "next": "string"
}
```

<h3 id="get__receipts_v4_users_{userid}_image-only-receipts_{state}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|JSON representing the receipts owned by this user. If no receipts are found for this user, an empty array of receipts is returned.|Inline|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Callers must provide a valid JWT and/or Concur-issued X.509 client certificate|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Caller does not have the required scope, or, depending on the type of JWT, may not have permission to access receipts for this specific user or company. In rare cases, this error code might mean that special functionality is limited to certain applications.|None|

<h3 id="get__receipts_v4_users_{userid}_image-only-receipts_{state}-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» imageOnlyReceipts|[[eReceipt](#schemaereceipt)]|false|none|none|
|»» modifiedAt|string|false|none|Timestamp corresponding to the last time the receipt record was modified|
|»» companyId|string|false|none|UUID of the company that the receipt owner belongs to|
|»» dateTimeReceived|string|false|none|Timestamp corresponding to when the receipt was saved to the system|
|»» entityId|string|false|none|Expense entityId of the company that the receipt owner belongs to|
|»» validationSchema|string|false|none|The JSON schema used to validate the E-receipt data|
|»» receipt|object|false|none|The actual data of the E-receipt|
|»» image|string|false|none|Link to the v4 copy of the image that corresponds to this E-receipt.|
|»» userId|string|false|none|The UUID of the user to whom the receipt belongs|
|»» id|string|false|none|An opaque string identifier for this receipt|
|»» digitizationStatus|string|false|none|Status of any back-end processing related to the digitization of a physical paper receipt.|
|»» forwardId|object|false|none|The forwardId, if one was submitted with the original POST request to create this receipt|
|»» self|string|false|none|Self-link for this receipt|
|»» template|string|false|none|URL template for this resource|
|» next|string|false|none|Link to the next page of receipts, if the response included the maximum of 50 receipts. The next page of receipts is available at this URL. If the next page also contains 50 receipt, it will also contain  a next page link, and so on.|

#### Enumerated Values

|Property|Value|
|---|---|
|validationSchema|http://schema.concursolutions.com/general-receipt.schema.json|
|validationSchema|http://schema.concursolutions.com/air-receipt.schema.json|
|validationSchema|http://schema.concursolutions.com/car-rental-receipt.schema.json|
|validationSchema|http://schema.concursolutions.com/ground-transport-receipt.schema.json|
|validationSchema|http://schema.concursolutions.com/hotel-receipt.schema.json|
|validationSchema|http://schema.concursolutions.com/jpt-ic-card-receipt.schema.json|
|validationSchema|http://schema.concursolutions.com/rail-receipt.schema.json|
|digitizationStatus|NO_PROCESSING_REQUIRED|
|digitizationStatus|PROCESSING|
|digitizationStatus|PROCESSED|
|digitizationStatus|FAILED|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None
</aside>

## get__receipts_v4_users_{userId}_image-only-receipts

> Code samples

```shell
# You can also use wget
curl -X GET https://us.api.concursolutions.com/receipts/v4/users/{userId}/image-only-receipts \
  -H 'Accept: application/json'

```

```http
GET https://us.api.concursolutions.com/receipts/v4/users/{userId}/image-only-receipts HTTP/1.1
Host: us.api.concursolutions.com
Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('https://us.api.concursolutions.com/receipts/v4/users/{userId}/image-only-receipts',
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
  'Accept' => 'application/json'
}

result = RestClient.get 'https://us.api.concursolutions.com/receipts/v4/users/{userId}/image-only-receipts',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://us.api.concursolutions.com/receipts/v4/users/{userId}/image-only-receipts', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','https://us.api.concursolutions.com/receipts/v4/users/{userId}/image-only-receipts', array(
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
URL obj = new URL("https://us.api.concursolutions.com/receipts/v4/users/{userId}/image-only-receipts");
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
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://us.api.concursolutions.com/receipts/v4/users/{userId}/image-only-receipts", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /receipts/v4/users/{userId}/image-only-receipts`

*Image-only receipts by userId*

Get all v4 image-only receipts for a single user. Maximum 50 receipts per page. If there are more results after the first page, a next page link will be provided in the results. Calling that link will retrieve the next page of receipts.

<h3 id="get__receipts_v4_users_{userid}_image-only-receipts-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|userId|path|string|true|UUID (not login ID) of the user|

> Example responses

> 200 Response

```json
{
  "imageOnlyReceipts": [
    {
      "modifiedAt": "string",
      "companyId": "string",
      "dateTimeReceived": "string",
      "entityId": "string",
      "digitizationData": {
        "captureMethod": "expenseItCapture",
        "hashCode": "string"
      },
      "image": "string",
      "userId": "string",
      "id": "string",
      "digitizationStatus": "NO_PROCESSING_REQUIRED",
      "forwardId": {},
      "self": "string",
      "template": "string"
    }
  ],
  "next": "string"
}
```

<h3 id="get__receipts_v4_users_{userid}_image-only-receipts-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|JSON representing the image-only receipts owned by this user. If no receipts are found for this user, an empty array of receipts is returned.|Inline|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Callers must provide a valid JWT and/or Concur-issued X.509 client certificate|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Caller does not have the required scope, or, depending on the type of JWT, may not have permission to access receipts for this specific user or company. In rare cases, this error code might mean that special functionality is limited to certain applications.|None|

<h3 id="get__receipts_v4_users_{userid}_image-only-receipts-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» imageOnlyReceipts|[[imageOnlyReceipt](#schemaimageonlyreceipt)]|false|none|none|
|»» modifiedAt|string|false|none|Timestamp corresponding to the last time the receipt record was modified|
|»» companyId|string|false|none|UUID of the company that the receipt owner belongs to|
|»» dateTimeReceived|string|false|none|Timestamp corresponding to when the receipt was saved to the system|
|»» entityId|string|false|none|Expense entityId of the company that the receipt owner belongs to|
|»» digitizationData|object|false|none|none|
|»»» captureMethod|string|false|none|The method used to capture this image of a paper receipt for digitization|
|»»» hashCode|string|false|none|SHA-512 hash of the image. Used to verify the provenance of the image.|
|»» image|string|false|none|Link to the v4 copy of the receipt image|
|»» userId|string|false|none|The UUID of the user to whom the receipt belongs|
|»» id|string|false|none|An opaque string identifier for this receipt|
|»» digitizationStatus|string|false|none|Status of any back-end processing related to the digitization of a physical paper receipt.|
|»» forwardId|object|false|none|The forwardId, if one was submitted with the original POST request to create this receipt|
|»» self|string|false|none|Self-link for this receipt|
|»» template|string|false|none|URL template for this resource|
|» next|string|false|none|Link to the next page of receipts, if the response included the maximum of 50 receipts. The next page of receipts is available at this URL. If the next page also contains 50 receipt, it will also contain  a next page link, and so on.|

#### Enumerated Values

|Property|Value|
|---|---|
|captureMethod|expenseItCapture|
|captureMethod|mobileCapture|
|digitizationStatus|NO_PROCESSING_REQUIRED|
|digitizationStatus|ACCEPTED|
|digitizationStatus|PROCESSING|
|digitizationStatus|PROCESSED|
|digitizationStatus|FAILED|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None
</aside>

## post__receipts_v4_users_{userId}_image-only-receipts

> Code samples

```shell
# You can also use wget
curl -X POST https://us.api.concursolutions.com/receipts/v4/users/{userId}/image-only-receipts \
  -H 'Content-Type: multipart/form-data'

```

```http
POST https://us.api.concursolutions.com/receipts/v4/users/{userId}/image-only-receipts HTTP/1.1
Host: us.api.concursolutions.com
Content-Type: multipart/form-data

```

```javascript
const inputBody = '{
  "image": "string",
  "clientData": "string",
  "forwardId": "string"
}';
const headers = {
  'Content-Type':'multipart/form-data'
};

fetch('https://us.api.concursolutions.com/receipts/v4/users/{userId}/image-only-receipts',
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
  'Content-Type' => 'multipart/form-data'
}

result = RestClient.post 'https://us.api.concursolutions.com/receipts/v4/users/{userId}/image-only-receipts',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'multipart/form-data'
}

r = requests.post('https://us.api.concursolutions.com/receipts/v4/users/{userId}/image-only-receipts', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'multipart/form-data',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','https://us.api.concursolutions.com/receipts/v4/users/{userId}/image-only-receipts', array(
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
URL obj = new URL("https://us.api.concursolutions.com/receipts/v4/users/{userId}/image-only-receipts");
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
        "Content-Type": []string{"multipart/form-data"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://us.api.concursolutions.com/receipts/v4/users/{userId}/image-only-receipts", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /receipts/v4/users/{userId}/image-only-receipts`

*New image-only receipt*

Create a new image-only receipt. Image-only receipts consist of an image without the JSON data that is included with E-receipts.

> Body parameter

```yaml
image: string
clientData: string
forwardId: string

```

<h3 id="post__receipts_v4_users_{userid}_image-only-receipts-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|userId|path|string|true|UUID (not login ID) of the user|
|body|body|object|true|none|
|» image|body|string(binary)|true|The receipt image|
|» clientData|body|string(binary)|false|Metadata about the capture of a paper receipt. Required for special GRDC processing rules to take effect. This parameter should be JSON. Please see the model for clientData for more details.|
|» forwardId|body|string|false|A user provided string of up to 40 characters used to identify a receipt submission. Should be unique from the  perspective of the client application. If a receipt is submitted with a forwardId that already exists in the system for that particular client, the request will be rejected with a 304 Not Modified response. This helps prevent duplicate receipt submissions from mobile clients.|

<h3 id="post__receipts_v4_users_{userid}_image-only-receipts-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|202|[Accepted](https://tools.ietf.org/html/rfc7231#section-6.3.3)|The receipt has been accepted and will be processed soon.|None|
|304|[Not Modified](https://tools.ietf.org/html/rfc7232#section-4.1)|The forwardId provided was already present in the system, indicating a duplicate receipt submission.|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request. The request was malformed or lacked required fields.|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Callers must provide a valid JWT and/or Concur-issued X.509 client certificate|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Caller does not have the required scope, or, depending on the type of JWT, may not have permission to access receipts for this specific user or company. In rare cases, this error code might mean that special functionality is limited to certain applications.|None|
|413|[Payload Too Large](https://tools.ietf.org/html/rfc7231#section-6.5.11)|The uploaded file was too large|None|
|415|[Unsupported Media Type](https://tools.ietf.org/html/rfc7231#section-6.5.13)|The content-type header was wrong, or the uploaded image was not of a supported type. Images must be .pdf, .png, .jpg, .jpeg, .tiff, or .gif.|None|

### Response Headers

|Status|Header|Type|Format|Description|
|---|---|---|---|---|
|202|Location|string||The URL location of the receipt. This link will return a 404 until the receipt has finished processing. After the receipt has finished processing, the receipt data will be available at this URL.|
|202|Link|string||Contains a link to status information about the receipt. Receipt processing happens asynchronously, so calling this link can provide information about the receipt if it has not yet shown up at the URL from the Location header.|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None
</aside>

## get__receipts_v4_users_{userId}_{state}

> Code samples

```shell
# You can also use wget
curl -X GET https://us.api.concursolutions.com/receipts/v4/users/{userId}/{state} \
  -H 'Accept: application/json'

```

```http
GET https://us.api.concursolutions.com/receipts/v4/users/{userId}/{state} HTTP/1.1
Host: us.api.concursolutions.com
Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('https://us.api.concursolutions.com/receipts/v4/users/{userId}/{state}',
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
  'Accept' => 'application/json'
}

result = RestClient.get 'https://us.api.concursolutions.com/receipts/v4/users/{userId}/{state}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://us.api.concursolutions.com/receipts/v4/users/{userId}/{state}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','https://us.api.concursolutions.com/receipts/v4/users/{userId}/{state}', array(
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
URL obj = new URL("https://us.api.concursolutions.com/receipts/v4/users/{userId}/{state}");
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
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://us.api.concursolutions.com/receipts/v4/users/{userId}/{state}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /receipts/v4/users/{userId}/{state}`

*Receipts for a user by state*

Get all v4 receipts for a single user with a certain state. Valid states are consumable (not attached to an expense report), consumed (attached), and discarded (deleted by the user). Maximum 50 receipts per page. If there are more results after the first page, a next page link will be provided in the results.  Calling that link will retrieve the next page of receipts.

<h3 id="get__receipts_v4_users_{userid}_{state}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|userId|path|string|true|UUID (not login ID) of the user|
|state|path|string|true|Desired state for the set of returned receipts. Valid states are consumable (not attached to an expense report), consumed (attached), and discarded (deleted by the user). Not to be confused with "status", which refers to the processing status of the receipt, not the state of the receipt within Expense.|

#### Enumerated Values

|Parameter|Value|
|---|---|
|state|consumed|
|state|consumable|
|state|discarded|

> Example responses

> 200 Response

```json
{
  "receipts": [
    {
      "modifiedAt": "string",
      "companyId": "string",
      "dateTimeReceived": "string",
      "entityId": "string",
      "validationSchema": "http://schema.concursolutions.com/general-receipt.schema.json",
      "receipt": {},
      "image": "string",
      "userId": "string",
      "id": "string",
      "digitizationStatus": "NO_PROCESSING_REQUIRED",
      "forwardId": {},
      "self": "string",
      "template": "string"
    }
  ],
  "next": "string"
}
```

<h3 id="get__receipts_v4_users_{userid}_{state}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|JSON representing the receipts owned by this user. If no receipts are found for this user, an empty array of receipts is returned.|Inline|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Callers must provide a valid JWT and/or Concur-issued X.509 client certificate|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Caller does not have the required scope, or, depending on the type of JWT, may not have permission to access receipts for this specific user or company. In rare cases, this error code might mean that special functionality is limited to certain applications.|None|

<h3 id="get__receipts_v4_users_{userid}_{state}-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» receipts|[[eReceipt](#schemaereceipt)]|false|none|none|
|»» modifiedAt|string|false|none|Timestamp corresponding to the last time the receipt record was modified|
|»» companyId|string|false|none|UUID of the company that the receipt owner belongs to|
|»» dateTimeReceived|string|false|none|Timestamp corresponding to when the receipt was saved to the system|
|»» entityId|string|false|none|Expense entityId of the company that the receipt owner belongs to|
|»» validationSchema|string|false|none|The JSON schema used to validate the E-receipt data|
|»» receipt|object|false|none|The actual data of the E-receipt|
|»» image|string|false|none|Link to the v4 copy of the image that corresponds to this E-receipt.|
|»» userId|string|false|none|The UUID of the user to whom the receipt belongs|
|»» id|string|false|none|An opaque string identifier for this receipt|
|»» digitizationStatus|string|false|none|Status of any back-end processing related to the digitization of a physical paper receipt.|
|»» forwardId|object|false|none|The forwardId, if one was submitted with the original POST request to create this receipt|
|»» self|string|false|none|Self-link for this receipt|
|»» template|string|false|none|URL template for this resource|
|» next|string|false|none|Link to the next page of receipts, if the response included the maximum of 50 receipts. The next page of receipts is available at this URL. If the next page also contains 50 receipt, it will also contain  a next page link, and so on.|

#### Enumerated Values

|Property|Value|
|---|---|
|validationSchema|http://schema.concursolutions.com/general-receipt.schema.json|
|validationSchema|http://schema.concursolutions.com/air-receipt.schema.json|
|validationSchema|http://schema.concursolutions.com/car-rental-receipt.schema.json|
|validationSchema|http://schema.concursolutions.com/ground-transport-receipt.schema.json|
|validationSchema|http://schema.concursolutions.com/hotel-receipt.schema.json|
|validationSchema|http://schema.concursolutions.com/jpt-ic-card-receipt.schema.json|
|validationSchema|http://schema.concursolutions.com/rail-receipt.schema.json|
|digitizationStatus|NO_PROCESSING_REQUIRED|
|digitizationStatus|PROCESSING|
|digitizationStatus|PROCESSED|
|digitizationStatus|FAILED|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None
</aside>

## post__receipts_v4_users_{userId}_{state}

> Code samples

```shell
# You can also use wget
curl -X POST https://us.api.concursolutions.com/receipts/v4/users/{userId}/{state} \
  -H 'Content-Type: application/json'

```

```http
POST https://us.api.concursolutions.com/receipts/v4/users/{userId}/{state} HTTP/1.1
Host: us.api.concursolutions.com
Content-Type: application/json

```

```javascript
const inputBody = '{
  "id": "string"
}';
const headers = {
  'Content-Type':'application/json'
};

fetch('https://us.api.concursolutions.com/receipts/v4/users/{userId}/{state}',
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
  'Content-Type' => 'application/json'
}

result = RestClient.post 'https://us.api.concursolutions.com/receipts/v4/users/{userId}/{state}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json'
}

r = requests.post('https://us.api.concursolutions.com/receipts/v4/users/{userId}/{state}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','https://us.api.concursolutions.com/receipts/v4/users/{userId}/{state}', array(
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
URL obj = new URL("https://us.api.concursolutions.com/receipts/v4/users/{userId}/{state}");
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
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://us.api.concursolutions.com/receipts/v4/users/{userId}/{state}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /receipts/v4/users/{userId}/{state}`

*Receipt state*

Change the state of a receipt. Valid states are consumable (not attached to an expense report), consumed (attached), and discarded (deleted by the user). This is an asynchronous operation, so the receipt state change might not take effect immediately.

> Body parameter

```json
{
  "id": "string"
}
```

<h3 id="post__receipts_v4_users_{userid}_{state}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|userId|path|string|true|UUID (not login ID) of the user|
|state|path|string|true|Desired state for the set of returned receipts. Valid states are consumable (not attached to an expense report), consumed (attached), and discarded (deleted by the user). Not to be confused with "status", which refers to the processing status of the receipt, not the state of the receipt within Expense.|
|body|body|[receiptIdObject](#schemareceiptidobject)|true|An object containing the id of the receipt to be modified|

#### Enumerated Values

|Parameter|Value|
|---|---|
|state|consumed|
|state|consumable|
|state|discarded|

<h3 id="post__receipts_v4_users_{userid}_{state}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|The state change request has been accepted. The new state might not be reflected immediately.|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request. Fix the request body and before trying again.|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Callers must provide a valid JWT and/or Concur-issued X.509 client certificate|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Caller does not have the required scope, or, depending on the type of JWT, may not have permission to access receipts for this specific user or company. In rare cases, this error code might mean that special functionality is limited to certain applications.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None
</aside>

## get__receipts_v4_users_{userId}

> Code samples

```shell
# You can also use wget
curl -X GET https://us.api.concursolutions.com/receipts/v4/users/{userId} \
  -H 'Accept: application/json'

```

```http
GET https://us.api.concursolutions.com/receipts/v4/users/{userId} HTTP/1.1
Host: us.api.concursolutions.com
Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('https://us.api.concursolutions.com/receipts/v4/users/{userId}',
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
  'Accept' => 'application/json'
}

result = RestClient.get 'https://us.api.concursolutions.com/receipts/v4/users/{userId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://us.api.concursolutions.com/receipts/v4/users/{userId}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','https://us.api.concursolutions.com/receipts/v4/users/{userId}', array(
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
URL obj = new URL("https://us.api.concursolutions.com/receipts/v4/users/{userId}");
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
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://us.api.concursolutions.com/receipts/v4/users/{userId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /receipts/v4/users/{userId}`

*Receipts by userId*

Get all v4 receipts for a single user. Maximum 50 receipts per page. If there are more results after the first page, a next page link will be provided in the results. Calling that link will retrieve the next page of receipts.

<h3 id="get__receipts_v4_users_{userid}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|userId|path|string|true|UUID (not login ID) of the user|

> Example responses

> 200 Response

```json
{
  "receipts": [
    {
      "modifiedAt": "string",
      "companyId": "string",
      "dateTimeReceived": "string",
      "entityId": "string",
      "validationSchema": "http://schema.concursolutions.com/general-receipt.schema.json",
      "receipt": {},
      "image": "string",
      "userId": "string",
      "id": "string",
      "digitizationStatus": "NO_PROCESSING_REQUIRED",
      "forwardId": {},
      "self": "string",
      "template": "string"
    }
  ],
  "next": "string"
}
```

<h3 id="get__receipts_v4_users_{userid}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|JSON representing the receipts owned by this user. If no receipts are found for this user, an empty array of receipts is returned.|Inline|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Callers must provide a valid JWT and/or Concur-issued X.509 client certificate|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Caller does not have the required scope, or, depending on the type of JWT, may not have permission to access receipts for this specific user or company. In rare cases, this error code might mean that special functionality is limited to certain applications.|None|

<h3 id="get__receipts_v4_users_{userid}-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» receipts|[[eReceipt](#schemaereceipt)]|false|none|none|
|»» modifiedAt|string|false|none|Timestamp corresponding to the last time the receipt record was modified|
|»» companyId|string|false|none|UUID of the company that the receipt owner belongs to|
|»» dateTimeReceived|string|false|none|Timestamp corresponding to when the receipt was saved to the system|
|»» entityId|string|false|none|Expense entityId of the company that the receipt owner belongs to|
|»» validationSchema|string|false|none|The JSON schema used to validate the E-receipt data|
|»» receipt|object|false|none|The actual data of the E-receipt|
|»» image|string|false|none|Link to the v4 copy of the image that corresponds to this E-receipt.|
|»» userId|string|false|none|The UUID of the user to whom the receipt belongs|
|»» id|string|false|none|An opaque string identifier for this receipt|
|»» digitizationStatus|string|false|none|Status of any back-end processing related to the digitization of a physical paper receipt.|
|»» forwardId|object|false|none|The forwardId, if one was submitted with the original POST request to create this receipt|
|»» self|string|false|none|Self-link for this receipt|
|»» template|string|false|none|URL template for this resource|
|» next|string|false|none|Link to the next page of receipts, if the response included the maximum of 50 receipts. The next page of receipts is available at this URL. If the next page also contains 50 receipt, it will also contain  a next page link, and so on.|

#### Enumerated Values

|Property|Value|
|---|---|
|validationSchema|http://schema.concursolutions.com/general-receipt.schema.json|
|validationSchema|http://schema.concursolutions.com/air-receipt.schema.json|
|validationSchema|http://schema.concursolutions.com/car-rental-receipt.schema.json|
|validationSchema|http://schema.concursolutions.com/ground-transport-receipt.schema.json|
|validationSchema|http://schema.concursolutions.com/hotel-receipt.schema.json|
|validationSchema|http://schema.concursolutions.com/jpt-ic-card-receipt.schema.json|
|validationSchema|http://schema.concursolutions.com/rail-receipt.schema.json|
|digitizationStatus|NO_PROCESSING_REQUIRED|
|digitizationStatus|PROCESSING|
|digitizationStatus|PROCESSED|
|digitizationStatus|FAILED|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None
</aside>

## post__receipts_v4_users_{userId}

> Code samples

```shell
# You can also use wget
curl -X POST https://us.api.concursolutions.com/receipts/v4/users/{userId} \
  -H 'Content-Type: multipart/form-data' \
  -H 'link: <http://schema.concursolutions.com/general-receipt.schema.json>;rel=describedBy'

```

```http
POST https://us.api.concursolutions.com/receipts/v4/users/{userId} HTTP/1.1
Host: us.api.concursolutions.com
Content-Type: multipart/form-data

link: <http://schema.concursolutions.com/general-receipt.schema.json>;rel=describedBy

```

```javascript
const inputBody = '{
  "receipt": "string",
  "image": "string"
}';
const headers = {
  'Content-Type':'multipart/form-data',
  'link':'<http://schema.concursolutions.com/general-receipt.schema.json>;rel=describedBy'
};

fetch('https://us.api.concursolutions.com/receipts/v4/users/{userId}',
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
  'Content-Type' => 'multipart/form-data',
  'link' => '<http://schema.concursolutions.com/general-receipt.schema.json>;rel=describedBy'
}

result = RestClient.post 'https://us.api.concursolutions.com/receipts/v4/users/{userId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'multipart/form-data',
  'link': '<http://schema.concursolutions.com/general-receipt.schema.json>;rel=describedBy'
}

r = requests.post('https://us.api.concursolutions.com/receipts/v4/users/{userId}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'multipart/form-data',
    'link' => '<http://schema.concursolutions.com/general-receipt.schema.json>;rel=describedBy',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','https://us.api.concursolutions.com/receipts/v4/users/{userId}', array(
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
URL obj = new URL("https://us.api.concursolutions.com/receipts/v4/users/{userId}");
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
        "Content-Type": []string{"multipart/form-data"},
        "link": []string{"<http://schema.concursolutions.com/general-receipt.schema.json>;rel=describedBy"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://us.api.concursolutions.com/receipts/v4/users/{userId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /receipts/v4/users/{userId}`

*New E-receipt*

Create a new E-receipt for a user.

> Body parameter

```yaml
receipt: string
image: string

```

<h3 id="post__receipts_v4_users_{userid}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|userId|path|string|true|UUID (not login ID) of the user|
|link|header|string|true|A link to the E-receipt schema to be used to validate the incoming E-receipt data. Retrieve the list of schemas from the GET schemas route.|
|body|body|object|true|none|
|» receipt|body|string|true|The JSON data for the receipt|
|» image|body|string(binary)|false|The image for this E-receipt. If no image is submitted, one will be generated automatically based on the JSON data.|

#### Enumerated Values

|Parameter|Value|
|---|---|
|link|<http://schema.concursolutions.com/general-receipt.schema.json>;rel=describedBy|
|link|<http://schema.concursolutions.com/car-rental-receipt.schema.json>;rel=describedBy|
|link|<http://schema.concursolutions.com/air-receipt.schema.json>;rel=describedBy|
|link|<http://schema.concursolutions.com/ground-transport-receipt.schema.json>;rel=describedBy|
|link|<http://schema.concursolutions.com/hotel-receipt.schema.json>;rel=describedBy|
|link|<http://schema.concursolutions.com/rail-receipt.schema.json>;rel=describedBy|

<h3 id="post__receipts_v4_users_{userid}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|The receipt has been accepted and will be processed soon.|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request. The request was malformed or lacked required fields.|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Callers must provide a valid JWT and/or Concur-issued X.509 client certificate|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Caller does not have the required scope, or, depending on the type of JWT, may not have permission to access receipts for this specific user or company. In rare cases, this error code might mean that special functionality is limited to certain applications.|None|
|413|[Payload Too Large](https://tools.ietf.org/html/rfc7231#section-6.5.11)|The uploaded file was too large|None|
|415|[Unsupported Media Type](https://tools.ietf.org/html/rfc7231#section-6.5.13)|The content-type header was wrong, or the uploaded image was not of a supported type. Images must be .pdf, .png, .jpg, .jpeg, .tiff, or .gif.|None|

### Response Headers

|Status|Header|Type|Format|Description|
|---|---|---|---|---|
|201|Location|string||The URL location of the receipt. This link will return a 404 until the receipt has finished processing. After the receipt has finished processing, the receipt data will be available at this URL.|
|201|Link|string||Contains two links: one with `rel="describedBy"` and one with `rel="processing-status"`. The describedBy link represents the JSON schema that was used to validate the receipt when it was submitted. This is the same link that was provided in the `schema` header in the request. The processing-status link can be called for status information about the receipt. Receipt processing happens asynchronously, so calling this link can provide information about the receipt if it has not yet shown up at the URL from the Location header.|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None
</aside>

# Schemas

<h2 id="tocS_receiptIdObject">receiptIdObject</h2>
<!-- backwards compatibility -->
<a id="schemareceiptidobject"></a>
<a id="schema_receiptIdObject"></a>
<a id="tocSreceiptidobject"></a>
<a id="tocsreceiptidobject"></a>

```json
{
  "id": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string|false|none|v4 receipt ID|

<h2 id="tocS_clientData">clientData</h2>
<!-- backwards compatibility -->
<a id="schemaclientdata"></a>
<a id="schema_clientData"></a>
<a id="tocSclientdata"></a>
<a id="tocsclientdata"></a>

```json
{
  "captureMethod": "mobileCapture",
  "hashCode": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|captureMethod|string|true|none|The method used to capture the image of the paper receipt. For images captured directly from the Concur mobile app using the device camera, use `mobileCapture` or `expenseItCapture` respectively, depending on whether or not expenseIt functionality is enabled for the user. The other capture methods, `mobileUpload` and `expenseItUpload`, are for images uploaded from the device local storage. In order to be eligible for digitization in France or Spain, images must be captured and cannot be uploaded from local storage.|
|hashCode|string|true|none|SHA512 hash of the image|

#### Enumerated Values

|Property|Value|
|---|---|
|captureMethod|mobileCapture|
|captureMethod|mobileUpload|
|captureMethod|expenseItCapture|
|captureMethod|expenseItUpload|

<h2 id="tocS_bulkStatusByReceiptId">bulkStatusByReceiptId</h2>
<!-- backwards compatibility -->
<a id="schemabulkstatusbyreceiptid"></a>
<a id="schema_bulkStatusByReceiptId"></a>
<a id="tocSbulkstatusbyreceiptid"></a>
<a id="tocsbulkstatusbyreceiptid"></a>

```json
{
  "receiptIds": [
    "string"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|receiptIds|[string]|true|none|Array of up to 50 receiptIds to retrieve status for|

<h2 id="tocS_bulkStatusByForwardId">bulkStatusByForwardId</h2>
<!-- backwards compatibility -->
<a id="schemabulkstatusbyforwardid"></a>
<a id="schema_bulkStatusByForwardId"></a>
<a id="tocSbulkstatusbyforwardid"></a>
<a id="tocsbulkstatusbyforwardid"></a>

```json
{
  "forwardIds": [
    "string"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|forwardIds|[string]|false|none|Array of forwardIds (max 50) associated with receipts. When using forwardIds receipts will only be retrievable if the caller uses the same auth mechanism used to post the receipt. If both a JWT and client cert were used, the JWT will take precedence|

<h2 id="tocS_linkObject">linkObject</h2>
<!-- backwards compatibility -->
<a id="schemalinkobject"></a>
<a id="schema_linkObject"></a>
<a id="tocSlinkobject"></a>
<a id="tocslinkobject"></a>

```json
{
  "rel": "string",
  "href": "string",
  "method": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|rel|string|false|none|HATEOAS "relationship" to the current resource|
|href|string|false|none|URI template for this resource|
|method|string|false|none|HTTP method to use against this resource|

<h2 id="tocS_eReceipt">eReceipt</h2>
<!-- backwards compatibility -->
<a id="schemaereceipt"></a>
<a id="schema_eReceipt"></a>
<a id="tocSereceipt"></a>
<a id="tocsereceipt"></a>

```json
{
  "modifiedAt": "string",
  "companyId": "string",
  "dateTimeReceived": "string",
  "entityId": "string",
  "validationSchema": "http://schema.concursolutions.com/general-receipt.schema.json",
  "receipt": {},
  "image": "string",
  "userId": "string",
  "id": "string",
  "digitizationStatus": "NO_PROCESSING_REQUIRED",
  "forwardId": {},
  "self": "string",
  "template": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|modifiedAt|string|false|none|Timestamp corresponding to the last time the receipt record was modified|
|companyId|string|false|none|UUID of the company that the receipt owner belongs to|
|dateTimeReceived|string|false|none|Timestamp corresponding to when the receipt was saved to the system|
|entityId|string|false|none|Expense entityId of the company that the receipt owner belongs to|
|validationSchema|string|false|none|The JSON schema used to validate the E-receipt data|
|receipt|object|false|none|The actual data of the E-receipt|
|image|string|false|none|Link to the v4 copy of the image that corresponds to this E-receipt.|
|userId|string|false|none|The UUID of the user to whom the receipt belongs|
|id|string|false|none|An opaque string identifier for this receipt|
|digitizationStatus|string|false|none|Status of any back-end processing related to the digitization of a physical paper receipt.|
|forwardId|object|false|none|The forwardId, if one was submitted with the original POST request to create this receipt|
|self|string|false|none|Self-link for this receipt|
|template|string|false|none|URL template for this resource|

#### Enumerated Values

|Property|Value|
|---|---|
|validationSchema|http://schema.concursolutions.com/general-receipt.schema.json|
|validationSchema|http://schema.concursolutions.com/air-receipt.schema.json|
|validationSchema|http://schema.concursolutions.com/car-rental-receipt.schema.json|
|validationSchema|http://schema.concursolutions.com/ground-transport-receipt.schema.json|
|validationSchema|http://schema.concursolutions.com/hotel-receipt.schema.json|
|validationSchema|http://schema.concursolutions.com/jpt-ic-card-receipt.schema.json|
|validationSchema|http://schema.concursolutions.com/rail-receipt.schema.json|
|digitizationStatus|NO_PROCESSING_REQUIRED|
|digitizationStatus|PROCESSING|
|digitizationStatus|PROCESSED|
|digitizationStatus|FAILED|

<h2 id="tocS_imageOnlyReceipt">imageOnlyReceipt</h2>
<!-- backwards compatibility -->
<a id="schemaimageonlyreceipt"></a>
<a id="schema_imageOnlyReceipt"></a>
<a id="tocSimageonlyreceipt"></a>
<a id="tocsimageonlyreceipt"></a>

```json
{
  "modifiedAt": "string",
  "companyId": "string",
  "dateTimeReceived": "string",
  "entityId": "string",
  "digitizationData": {
    "captureMethod": "expenseItCapture",
    "hashCode": "string"
  },
  "image": "string",
  "userId": "string",
  "id": "string",
  "digitizationStatus": "NO_PROCESSING_REQUIRED",
  "forwardId": {},
  "self": "string",
  "template": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|modifiedAt|string|false|none|Timestamp corresponding to the last time the receipt record was modified|
|companyId|string|false|none|UUID of the company that the receipt owner belongs to|
|dateTimeReceived|string|false|none|Timestamp corresponding to when the receipt was saved to the system|
|entityId|string|false|none|Expense entityId of the company that the receipt owner belongs to|
|digitizationData|object|false|none|none|
|» captureMethod|string|false|none|The method used to capture this image of a paper receipt for digitization|
|» hashCode|string|false|none|SHA-512 hash of the image. Used to verify the provenance of the image.|
|image|string|false|none|Link to the v4 copy of the receipt image|
|userId|string|false|none|The UUID of the user to whom the receipt belongs|
|id|string|false|none|An opaque string identifier for this receipt|
|digitizationStatus|string|false|none|Status of any back-end processing related to the digitization of a physical paper receipt.|
|forwardId|object|false|none|The forwardId, if one was submitted with the original POST request to create this receipt|
|self|string|false|none|Self-link for this receipt|
|template|string|false|none|URL template for this resource|

#### Enumerated Values

|Property|Value|
|---|---|
|captureMethod|expenseItCapture|
|captureMethod|mobileCapture|
|digitizationStatus|NO_PROCESSING_REQUIRED|
|digitizationStatus|ACCEPTED|
|digitizationStatus|PROCESSING|
|digitizationStatus|PROCESSED|
|digitizationStatus|FAILED|

<h2 id="tocS_sdr">sdr</h2>
<!-- backwards compatibility -->
<a id="schemasdr"></a>
<a id="schema_sdr"></a>
<a id="tocSsdr"></a>
<a id="tocssdr"></a>

```json
{
  "invoiceNumber": "string",
  "invoiceType": "FA",
  "supplierName": "string",
  "supplierTaxId": "string",
  "supplierAddress": {
    "streetAddress": "string",
    "addressLocality": "string",
    "addressRegion": "string",
    "addressCountry": "st",
    "postalCode": "st"
  },
  "transactionDate": "string",
  "issueDate": "string",
  "taxes": [
    {
      "taxRate": "string",
      "taxBase": "string",
      "rateType": "reduced",
      "amount": "string"
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|invoiceNumber|string|false|none|none|
|invoiceType|string|false|none|Invoice Types for Spain. FA, FC, & OT represent a Simplified Invoice, a Full Invoice, and Other respectively|
|supplierName|string|false|none|none|
|supplierTaxId|string|false|none|none|
|supplierAddress|object|false|none|none|
|» streetAddress|string|false|none|none|
|» addressLocality|string|false|none|none|
|» addressRegion|string|false|none|none|
|» addressCountry|string|false|none|2-character country code|
|» postalCode|string|false|none|none|
|transactionDate|string|false|none|none|
|issueDate|string|false|none|none|
|taxes|[object]|false|none|none|
|» taxRate|string|false|none|String representation of Tax Rate as a decimal.|
|» taxBase|string|false|none|none|
|» rateType|string|true|none|The rate type for the tax charged. For value added tax this could be Reduced, Super Reduced, Standard, or Parking.|
|» amount|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|invoiceType|FA|
|invoiceType|FC|
|invoiceType|OT|
|rateType|reduced|
|rateType|superReduced|
|rateType|standard|
|rateType|parking|

