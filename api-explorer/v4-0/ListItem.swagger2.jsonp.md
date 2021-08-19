<!-- Generator: Widdershins v4.0.1 -->

<h1 id="list-item">List Item v4.0</h1>

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

Provides an automated solution to clients who would like to manage list items. This API provides methods to view, add, update or delete list items owned by the specified lists.

Base URLs:

* <a href="https://www.concursolutions.com/api/v4.0">https://www.concursolutions.com/api/v4.0</a>

<h1 id="list-item-list-item-api">List Item API</h1>

List Item Controller

## createListItemUsingPOST

<a id="opIdcreateListItemUsingPOST"></a>

> Code samples

```shell
# You can also use wget
curl -X POST https://www.concursolutions.com/api/v4.0/list/v4/items \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Accept-Language: string'

```

```http
POST https://www.concursolutions.com/api/v4.0/list/v4/items HTTP/1.1
Host: www.concursolutions.com
Content-Type: application/json
Accept: application/json
Accept-Language: string

```

```javascript
const inputBody = '{
  "listId": "9fc6ad7d-902a-4834-b161-a4911b883d44",
  "parentCode": "string",
  "parentId": "70850378-7d3c-4f45-91b7-942d4dfbbd43",
  "shortCode": "string",
  "value": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Accept-Language':'string'
};

fetch('https://www.concursolutions.com/api/v4.0/list/v4/items',
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
  'Accept-Language' => 'string'
}

result = RestClient.post 'https://www.concursolutions.com/api/v4.0/list/v4/items',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Accept-Language': 'string'
}

r = requests.post('https://www.concursolutions.com/api/v4.0/list/v4/items', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'Accept-Language' => 'string',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','https://www.concursolutions.com/api/v4.0/list/v4/items', array(
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
URL obj = new URL("https://www.concursolutions.com/api/v4.0/list/v4/items");
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
        "Accept-Language": []string{"string"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://www.concursolutions.com/api/v4.0/list/v4/items", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /list/v4/items`

*Create a list item with provided request body*

Returns the newly created list item

> Body parameter

```json
{
  "listId": "9fc6ad7d-902a-4834-b161-a4911b883d44",
  "parentCode": "string",
  "parentId": "70850378-7d3c-4f45-91b7-942d4dfbbd43",
  "shortCode": "string",
  "value": "string"
}
```

<h3 id="createlistitemusingpost-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|Accept-Language|header|string|false|Language code|
|body|body|[ListItemCreate](#schemalistitemcreate)|true|List Item object that is created for the company|

> Example responses

> 201 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "code": "string",
  "shortCode": "string",
  "value": "string",
  "parentId": "70850378-7d3c-4f45-91b7-942d4dfbbd43",
  "listId": "9fc6ad7d-902a-4834-b161-a4911b883d44",
  "level": 1,
  "lists": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "hasChildren": true
    }
  ],
  "isDeleted": true
}
```

<h3 id="createlistitemusingpost-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Successfully created the list item|[ListItem](#schemalistitem)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[ErrorMessage](#schemaerrormessage)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Access Denied|[ErrorMessage](#schemaerrormessage)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[ErrorMessage](#schemaerrormessage)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|List not found|[ErrorMessage](#schemaerrormessage)|
|415|[Unsupported Media Type](https://tools.ietf.org/html/rfc7231#section-6.5.13)|The specified media type is not supported|[ErrorMessage](#schemaerrormessage)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal server error|[ErrorMessage](#schemaerrormessage)|

<aside class="success">
This operation does not require authentication
</aside>

## getListItemUsingGET

<a id="opIdgetListItemUsingGET"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://www.concursolutions.com/api/v4.0/list/v4/items/{itemId} \
  -H 'Accept: application/json' \
  -H 'Accept-Language: string'

```

```http
GET https://www.concursolutions.com/api/v4.0/list/v4/items/{itemId} HTTP/1.1
Host: www.concursolutions.com
Accept: application/json
Accept-Language: string

```

```javascript

const headers = {
  'Accept':'application/json',
  'Accept-Language':'string'
};

fetch('https://www.concursolutions.com/api/v4.0/list/v4/items/{itemId}',
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
  'Accept-Language' => 'string'
}

result = RestClient.get 'https://www.concursolutions.com/api/v4.0/list/v4/items/{itemId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Accept-Language': 'string'
}

r = requests.get('https://www.concursolutions.com/api/v4.0/list/v4/items/{itemId}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'Accept-Language' => 'string',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','https://www.concursolutions.com/api/v4.0/list/v4/items/{itemId}', array(
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
URL obj = new URL("https://www.concursolutions.com/api/v4.0/list/v4/items/{itemId}");
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
        "Accept-Language": []string{"string"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://www.concursolutions.com/api/v4.0/list/v4/items/{itemId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /list/v4/items/{itemId}`

*Get a list item by ID*

Returns the list item

<h3 id="getlistitemusingget-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|Accept-Language|header|string|false|Language code|
|itemId|path|string(uuid)|true|The unique identifier of the list item|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "code": "string",
  "shortCode": "string",
  "value": "string",
  "parentId": "70850378-7d3c-4f45-91b7-942d4dfbbd43",
  "listId": "9fc6ad7d-902a-4834-b161-a4911b883d44",
  "level": 1,
  "lists": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "hasChildren": true
    }
  ],
  "isDeleted": true
}
```

<h3 id="getlistitemusingget-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successfully get list item|[ListItem](#schemalistitem)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Company does not exist|[ErrorMessage](#schemaerrormessage)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Access Denied|[ErrorMessage](#schemaerrormessage)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|listItem not found|[ErrorMessage](#schemaerrormessage)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal server error|[ErrorMessage](#schemaerrormessage)|

<aside class="success">
This operation does not require authentication
</aside>

## updateListItemUsingPUT

<a id="opIdupdateListItemUsingPUT"></a>

> Code samples

```shell
# You can also use wget
curl -X PUT https://www.concursolutions.com/api/v4.0/list/v4/items/{itemId} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Accept-Language: string'

```

```http
PUT https://www.concursolutions.com/api/v4.0/list/v4/items/{itemId} HTTP/1.1
Host: www.concursolutions.com
Content-Type: application/json
Accept: application/json
Accept-Language: string

```

```javascript
const inputBody = '{
  "shortCode": "string",
  "value": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Accept-Language':'string'
};

fetch('https://www.concursolutions.com/api/v4.0/list/v4/items/{itemId}',
{
  method: 'PUT',
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
  'Accept-Language' => 'string'
}

result = RestClient.put 'https://www.concursolutions.com/api/v4.0/list/v4/items/{itemId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Accept-Language': 'string'
}

r = requests.put('https://www.concursolutions.com/api/v4.0/list/v4/items/{itemId}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'Accept-Language' => 'string',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('PUT','https://www.concursolutions.com/api/v4.0/list/v4/items/{itemId}', array(
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
URL obj = new URL("https://www.concursolutions.com/api/v4.0/list/v4/items/{itemId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PUT");
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
        "Accept-Language": []string{"string"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PUT", "https://www.concursolutions.com/api/v4.0/list/v4/items/{itemId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PUT /list/v4/items/{itemId}`

*Update a list item with provided request body*

Returns the updated list item

> Body parameter

```json
{
  "shortCode": "string",
  "value": "string"
}
```

<h3 id="updatelistitemusingput-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|Accept-Language|header|string|false|Language code|
|itemId|path|string(uuid)|true|The unique identifier of the list item|
|body|body|[ListItemUpdate](#schemalistitemupdate)|true|List item|

> Example responses

> 200 Response

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "code": "string",
  "shortCode": "string",
  "value": "string",
  "parentId": "70850378-7d3c-4f45-91b7-942d4dfbbd43",
  "listId": "9fc6ad7d-902a-4834-b161-a4911b883d44",
  "level": 1,
  "lists": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "hasChildren": true
    }
  ],
  "isDeleted": true
}
```

<h3 id="updatelistitemusingput-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successfully updated list item|[ListItem](#schemalistitem)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Company does not exist|[ErrorMessage](#schemaerrormessage)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Access Denied|[ErrorMessage](#schemaerrormessage)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[ErrorMessage](#schemaerrormessage)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|listItem not found|[ErrorMessage](#schemaerrormessage)|
|415|[Unsupported Media Type](https://tools.ietf.org/html/rfc7231#section-6.5.13)|The specified media type is not supported|[ErrorMessage](#schemaerrormessage)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal server error|[ErrorMessage](#schemaerrormessage)|

<aside class="success">
This operation does not require authentication
</aside>

## deleteListItemUsingDELETE

<a id="opIddeleteListItemUsingDELETE"></a>

> Code samples

```shell
# You can also use wget
curl -X DELETE https://www.concursolutions.com/api/v4.0/list/v4/items/{itemId} \
  -H 'Accept: application/json'

```

```http
DELETE https://www.concursolutions.com/api/v4.0/list/v4/items/{itemId} HTTP/1.1
Host: www.concursolutions.com
Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('https://www.concursolutions.com/api/v4.0/list/v4/items/{itemId}',
{
  method: 'DELETE',

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

result = RestClient.delete 'https://www.concursolutions.com/api/v4.0/list/v4/items/{itemId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.delete('https://www.concursolutions.com/api/v4.0/list/v4/items/{itemId}', headers = headers)

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
    $response = $client->request('DELETE','https://www.concursolutions.com/api/v4.0/list/v4/items/{itemId}', array(
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
URL obj = new URL("https://www.concursolutions.com/api/v4.0/list/v4/items/{itemId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
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
    req, err := http.NewRequest("DELETE", "https://www.concursolutions.com/api/v4.0/list/v4/items/{itemId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`DELETE /list/v4/items/{itemId}`

*Delete a list item by ID*

Returns a status code result

<h3 id="deletelistitemusingdelete-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|itemId|path|string(uuid)|true|The unique identifier of the list item|

> Example responses

> 400 Response

```json
{
  "error": {
    "id": "string",
    "message": "string"
  },
  "httpStatus": "string",
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

<h3 id="deletelistitemusingdelete-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|Successfully deleted list item|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Company does not exist|[ErrorMessage](#schemaerrormessage)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Access Denied|[ErrorMessage](#schemaerrormessage)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[ErrorMessage](#schemaerrormessage)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal server error|[ErrorMessage](#schemaerrormessage)|

<aside class="success">
This operation does not require authentication
</aside>

## getChildrenUsingGET

<a id="opIdgetChildrenUsingGET"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://www.concursolutions.com/api/v4.0/list/v4/items/{itemId}/children \
  -H 'Accept: application/json' \
  -H 'Accept-Language: string'

```

```http
GET https://www.concursolutions.com/api/v4.0/list/v4/items/{itemId}/children HTTP/1.1
Host: www.concursolutions.com
Accept: application/json
Accept-Language: string

```

```javascript

const headers = {
  'Accept':'application/json',
  'Accept-Language':'string'
};

fetch('https://www.concursolutions.com/api/v4.0/list/v4/items/{itemId}/children',
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
  'Accept-Language' => 'string'
}

result = RestClient.get 'https://www.concursolutions.com/api/v4.0/list/v4/items/{itemId}/children',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Accept-Language': 'string'
}

r = requests.get('https://www.concursolutions.com/api/v4.0/list/v4/items/{itemId}/children', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'Accept-Language' => 'string',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','https://www.concursolutions.com/api/v4.0/list/v4/items/{itemId}/children', array(
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
URL obj = new URL("https://www.concursolutions.com/api/v4.0/list/v4/items/{itemId}/children");
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
        "Accept-Language": []string{"string"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://www.concursolutions.com/api/v4.0/list/v4/items/{itemId}/children", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /list/v4/items/{itemId}/children`

*Get the direct children of a list item*

Returns the list item children

<h3 id="getchildrenusingget-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|Accept-Language|header|string|false|Language code|
|hasChildren|query|boolean|false|Show items with children|
|isDeleted|query|boolean|false|Show deleted items|
|itemId|path|string(uuid)|true|The unique identifier of the list item|
|page|query|integer(int32)|false|Page number starting from 1|
|shortCode|query|string|false|Filter capabilities for ShortCode|
|shortCodeOrValue|query|string|false|Filter capabilities for Value OR ShortCode|
|sortBy|query|string|false|Field to sort by, {value, shortcode}|
|sortDirection|query|string|false|Sort direction, {asc, desc}|
|value|query|string|false|Filter capabilities for Value|

#### Enumerated Values

|Parameter|Value|
|---|---|
|sortBy|value|
|sortBy|shortcode|
|sortDirection|asc|
|sortDirection|desc|

> Example responses

> 200 Response

```json
{
  "content": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "code": "string",
      "shortCode": "string",
      "value": "string",
      "parentId": "70850378-7d3c-4f45-91b7-942d4dfbbd43",
      "listId": "9fc6ad7d-902a-4834-b161-a4911b883d44",
      "level": 1,
      "lists": [
        {
          "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
          "hasChildren": true
        }
      ],
      "isDeleted": true
    }
  ],
  "links": [
    {
      "href": "string",
      "rel": "string"
    }
  ],
  "page": {
    "number": 1,
    "size": 100,
    "totalElements": 1,
    "totalPages": 1
  }
}
```

<h3 id="getchildrenusingget-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successfully got children of list item|[PagedResourcesListItem](#schemapagedresourceslistitem)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Company does not exist|[ErrorMessage](#schemaerrormessage)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Access Denied|[ErrorMessage](#schemaerrormessage)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|listItem not found|[ErrorMessage](#schemaerrormessage)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal server error|[ErrorMessage](#schemaerrormessage)|

<aside class="success">
This operation does not require authentication
</aside>

## getFirstLevelListItemsUsingGET

<a id="opIdgetFirstLevelListItemsUsingGET"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://www.concursolutions.com/api/v4.0/list/v4/lists/{listId}/children \
  -H 'Accept: application/json' \
  -H 'Accept-Language: string'

```

```http
GET https://www.concursolutions.com/api/v4.0/list/v4/lists/{listId}/children HTTP/1.1
Host: www.concursolutions.com
Accept: application/json
Accept-Language: string

```

```javascript

const headers = {
  'Accept':'application/json',
  'Accept-Language':'string'
};

fetch('https://www.concursolutions.com/api/v4.0/list/v4/lists/{listId}/children',
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
  'Accept-Language' => 'string'
}

result = RestClient.get 'https://www.concursolutions.com/api/v4.0/list/v4/lists/{listId}/children',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Accept-Language': 'string'
}

r = requests.get('https://www.concursolutions.com/api/v4.0/list/v4/lists/{listId}/children', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'Accept-Language' => 'string',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','https://www.concursolutions.com/api/v4.0/list/v4/lists/{listId}/children', array(
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
URL obj = new URL("https://www.concursolutions.com/api/v4.0/list/v4/lists/{listId}/children");
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
        "Accept-Language": []string{"string"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://www.concursolutions.com/api/v4.0/list/v4/lists/{listId}/children", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /list/v4/lists/{listId}/children`

*Get the first level list items for a given List ID*

Returns the first level children list items for a list

<h3 id="getfirstlevellistitemsusingget-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|Accept-Language|header|string|false|Language code|
|hasChildren|query|boolean|false|Show items with children|
|isDeleted|query|boolean|false|Show deleted items|
|listId|path|string(uuid)|true|The unique identifier of the list|
|page|query|integer(int32)|false|Page number starting from 1|
|shortCode|query|string|false|Filter capabilities for ShortCode|
|shortCodeOrValue|query|string|false|Filter capabilities for Value OR ShortCode|
|sortBy|query|string|false|Field to sort by, {value, shortcode}|
|sortDirection|query|string|false|Sort direction, {asc, desc}|
|value|query|string|false|Filter capabilities for Value|

#### Enumerated Values

|Parameter|Value|
|---|---|
|sortBy|value|
|sortBy|shortcode|
|sortDirection|asc|
|sortDirection|desc|

> Example responses

> 200 Response

```json
{
  "content": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "code": "string",
      "shortCode": "string",
      "value": "string",
      "parentId": "70850378-7d3c-4f45-91b7-942d4dfbbd43",
      "listId": "9fc6ad7d-902a-4834-b161-a4911b883d44",
      "level": 1,
      "lists": [
        {
          "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
          "hasChildren": true
        }
      ],
      "isDeleted": true
    }
  ],
  "links": [
    {
      "href": "string",
      "rel": "string"
    }
  ],
  "page": {
    "number": 1,
    "size": 100,
    "totalElements": 1,
    "totalPages": 1
  }
}
```

<h3 id="getfirstlevellistitemsusingget-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successfully got first level list items of list|[PagedResourcesListItem](#schemapagedresourceslistitem)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Company does not exist|[ErrorMessage](#schemaerrormessage)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Access Denied|[ErrorMessage](#schemaerrormessage)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|List not found|[ErrorMessage](#schemaerrormessage)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal server error|[ErrorMessage](#schemaerrormessage)|

<aside class="success">
This operation does not require authentication
</aside>

## deleteListItemFromListUsingDELETE

<a id="opIddeleteListItemFromListUsingDELETE"></a>

> Code samples

```shell
# You can also use wget
curl -X DELETE https://www.concursolutions.com/api/v4.0/list/v4/lists/{listId}/items/{itemId} \
  -H 'Accept: application/json'

```

```http
DELETE https://www.concursolutions.com/api/v4.0/list/v4/lists/{listId}/items/{itemId} HTTP/1.1
Host: www.concursolutions.com
Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('https://www.concursolutions.com/api/v4.0/list/v4/lists/{listId}/items/{itemId}',
{
  method: 'DELETE',

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

result = RestClient.delete 'https://www.concursolutions.com/api/v4.0/list/v4/lists/{listId}/items/{itemId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.delete('https://www.concursolutions.com/api/v4.0/list/v4/lists/{listId}/items/{itemId}', headers = headers)

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
    $response = $client->request('DELETE','https://www.concursolutions.com/api/v4.0/list/v4/lists/{listId}/items/{itemId}', array(
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
URL obj = new URL("https://www.concursolutions.com/api/v4.0/list/v4/lists/{listId}/items/{itemId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
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
    req, err := http.NewRequest("DELETE", "https://www.concursolutions.com/api/v4.0/list/v4/lists/{listId}/items/{itemId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`DELETE /list/v4/lists/{listId}/items/{itemId}`

*Delete a list item by list item ID from a particular list*

Returns a status code result

<h3 id="deletelistitemfromlistusingdelete-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|listId|path|string(uuid)|true|The unique identifier of the list|
|itemId|path|string(uuid)|true|The unique identifier of the list item|

> Example responses

> 400 Response

```json
{
  "error": {
    "id": "string",
    "message": "string"
  },
  "httpStatus": "string",
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

<h3 id="deletelistitemfromlistusingdelete-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|Successfully deleted list item with list ID|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Company does not exist|[ErrorMessage](#schemaerrormessage)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Access Denied|[ErrorMessage](#schemaerrormessage)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[ErrorMessage](#schemaerrormessage)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal server error|[ErrorMessage](#schemaerrormessage)|

<aside class="success">
This operation does not require authentication
</aside>

## getChildrenInListUsingGET

<a id="opIdgetChildrenInListUsingGET"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://www.concursolutions.com/api/v4.0/list/v4/lists/{listId}/items/{itemId}/children \
  -H 'Accept: application/json' \
  -H 'Accept-Language: string'

```

```http
GET https://www.concursolutions.com/api/v4.0/list/v4/lists/{listId}/items/{itemId}/children HTTP/1.1
Host: www.concursolutions.com
Accept: application/json
Accept-Language: string

```

```javascript

const headers = {
  'Accept':'application/json',
  'Accept-Language':'string'
};

fetch('https://www.concursolutions.com/api/v4.0/list/v4/lists/{listId}/items/{itemId}/children',
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
  'Accept-Language' => 'string'
}

result = RestClient.get 'https://www.concursolutions.com/api/v4.0/list/v4/lists/{listId}/items/{itemId}/children',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Accept-Language': 'string'
}

r = requests.get('https://www.concursolutions.com/api/v4.0/list/v4/lists/{listId}/items/{itemId}/children', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'Accept-Language' => 'string',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','https://www.concursolutions.com/api/v4.0/list/v4/lists/{listId}/items/{itemId}/children', array(
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
URL obj = new URL("https://www.concursolutions.com/api/v4.0/list/v4/lists/{listId}/items/{itemId}/children");
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
        "Accept-Language": []string{"string"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://www.concursolutions.com/api/v4.0/list/v4/lists/{listId}/items/{itemId}/children", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /list/v4/lists/{listId}/items/{itemId}/children`

*Get the direct children of a list item in a particular list*

Returns the list item children

<h3 id="getchildreninlistusingget-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|Accept-Language|header|string|false|Language code|
|hasChildren|query|boolean|false|Show items with children|
|isDeleted|query|boolean|false|Show deleted items|
|itemId|path|string(uuid)|true|The unique identifier of the list item|
|listId|path|string(uuid)|true|The unique identifier of the list. For a list item shared between multiple lists, this parameter enables retrieving children from a particular list.|
|page|query|integer(int32)|false|Page number starting from 1|
|shortCode|query|string|false|Filter capabilities for ShortCode|
|shortCodeOrValue|query|string|false|Filter capabilities for Value OR ShortCode|
|sortBy|query|string|false|Field to sort by, {value, shortcode}|
|sortDirection|query|string|false|Sort direction, {asc, desc}|
|value|query|string|false|Filter capabilities for Value|

#### Enumerated Values

|Parameter|Value|
|---|---|
|sortBy|value|
|sortBy|shortcode|
|sortDirection|asc|
|sortDirection|desc|

> Example responses

> 200 Response

```json
{
  "content": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "code": "string",
      "shortCode": "string",
      "value": "string",
      "parentId": "70850378-7d3c-4f45-91b7-942d4dfbbd43",
      "listId": "9fc6ad7d-902a-4834-b161-a4911b883d44",
      "level": 1,
      "lists": [
        {
          "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
          "hasChildren": true
        }
      ],
      "isDeleted": true
    }
  ],
  "links": [
    {
      "href": "string",
      "rel": "string"
    }
  ],
  "page": {
    "number": 1,
    "size": 100,
    "totalElements": 1,
    "totalPages": 1
  }
}
```

<h3 id="getchildreninlistusingget-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successfully got children of list item|[PagedResourcesListItem](#schemapagedresourceslistitem)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Company does not exist|[ErrorMessage](#schemaerrormessage)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Access Denied|[ErrorMessage](#schemaerrormessage)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|listItem not found|[ErrorMessage](#schemaerrormessage)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal server error|[ErrorMessage](#schemaerrormessage)|

<aside class="success">
This operation does not require authentication
</aside>

# Schemas

<h2 id="tocS_ErrorMessage">ErrorMessage</h2>
<!-- backwards compatibility -->
<a id="schemaerrormessage"></a>
<a id="schema_ErrorMessage"></a>
<a id="tocSerrormessage"></a>
<a id="tocserrormessage"></a>

```json
{
  "error": {
    "id": "string",
    "message": "string"
  },
  "httpStatus": "string",
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
|error|[Message](#schemamessage)|true|none|none|
|httpStatus|string|true|none|The http response code and phrase for the response|
|path|string|true|none|The URI of the attempted request|
|timestamp|string(date-time)|true|none|The time when the error was captured|
|validationErrors|[[ValidationError](#schemavalidationerror)]|false|none|The validation error messages|

<h2 id="tocS_Link">Link</h2>
<!-- backwards compatibility -->
<a id="schemalink"></a>
<a id="schema_Link"></a>
<a id="tocSlink"></a>
<a id="tocslink"></a>

```json
{
  "href": "string",
  "rel": "string"
}

```

Link

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|href|string|false|none|none|
|rel|string|false|none|none|

<h2 id="tocS_ListItem">ListItem</h2>
<!-- backwards compatibility -->
<a id="schemalistitem"></a>
<a id="schema_ListItem"></a>
<a id="tocSlistitem"></a>
<a id="tocslistitem"></a>

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "code": "string",
  "shortCode": "string",
  "value": "string",
  "parentId": "70850378-7d3c-4f45-91b7-942d4dfbbd43",
  "listId": "9fc6ad7d-902a-4834-b161-a4911b883d44",
  "level": 1,
  "lists": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "hasChildren": true
    }
  ],
  "isDeleted": true
}

```

ListItem

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|false|none|The unique identifier of the list item|
|code|string|false|none|List item long code|
|shortCode|string|false|none|List item short code|
|value|string|false|none|List item value|
|parentId|string(uuid)|false|none|The unique identifier of the parent list item|
|listId|string(uuid)|false|none|The unique identifier of the list that contains the list item|
|level|integer(int32)|false|none|Level of the list item within the list|
|lists|[[ListItemMemberList](#schemalistitemmemberlist)]|false|none|The unique identifiers of the lists that contains the list item|
|isDeleted|boolean|false|none|Whether the list item has been deleted|

<h2 id="tocS_ListItemCreate">ListItemCreate</h2>
<!-- backwards compatibility -->
<a id="schemalistitemcreate"></a>
<a id="schema_ListItemCreate"></a>
<a id="tocSlistitemcreate"></a>
<a id="tocslistitemcreate"></a>

```json
{
  "listId": "9fc6ad7d-902a-4834-b161-a4911b883d44",
  "parentCode": "string",
  "parentId": "70850378-7d3c-4f45-91b7-942d4dfbbd43",
  "shortCode": "string",
  "value": "string"
}

```

ListItemCreate

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|listId|string(uuid)|true|none|The unique identifier of the list that contains the list item|
|parentCode|string|false|none|The long code of parent list item|
|parentId|string(uuid)|false|none|The unique identifier of parent list item|
|shortCode|string|true|none|List item short code|
|value|string|true|none|List item value|

<h2 id="tocS_ListItemMemberList">ListItemMemberList</h2>
<!-- backwards compatibility -->
<a id="schemalistitemmemberlist"></a>
<a id="schema_ListItemMemberList"></a>
<a id="tocSlistitemmemberlist"></a>
<a id="tocslistitemmemberlist"></a>

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "hasChildren": true
}

```

ListItemMemberList

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|false|none|The unique identifier of the list that contains the list item|
|hasChildren|boolean|false|none|Whether the list item has children in this particular list|

<h2 id="tocS_ListItemUpdate">ListItemUpdate</h2>
<!-- backwards compatibility -->
<a id="schemalistitemupdate"></a>
<a id="schema_ListItemUpdate"></a>
<a id="tocSlistitemupdate"></a>
<a id="tocslistitemupdate"></a>

```json
{
  "shortCode": "string",
  "value": "string"
}

```

ListItemUpdate

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|shortCode|string|true|none|List item short code|
|value|string|true|none|List item value|

<h2 id="tocS_Message">Message</h2>
<!-- backwards compatibility -->
<a id="schemamessage"></a>
<a id="schema_Message"></a>
<a id="tocSmessage"></a>
<a id="tocsmessage"></a>

```json
{
  "id": "string",
  "message": "string"
}

```

Message

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string|false|none|The unique identifier of the error associated with the response or is it error response itself|
|message|string|false|none|none|

<h2 id="tocS_PageMetadata">PageMetadata</h2>
<!-- backwards compatibility -->
<a id="schemapagemetadata"></a>
<a id="schema_PageMetadata"></a>
<a id="tocSpagemetadata"></a>
<a id="tocspagemetadata"></a>

```json
{
  "number": 1,
  "size": 100,
  "totalElements": 1,
  "totalPages": 1
}

```

PageMetadata

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|number|integer(int64)|false|none|none|
|size|integer(int64)|false|none|none|
|totalElements|integer(int64)|false|none|none|
|totalPages|integer(int64)|false|none|none|

<h2 id="tocS_PagedResourcesListItem">PagedResourcesListItem</h2>
<!-- backwards compatibility -->
<a id="schemapagedresourceslistitem"></a>
<a id="schema_PagedResourcesListItem"></a>
<a id="tocSpagedresourceslistitem"></a>
<a id="tocspagedresourceslistitem"></a>

```json
{
  "content": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "code": "string",
      "shortCode": "string",
      "value": "string",
      "parentId": "70850378-7d3c-4f45-91b7-942d4dfbbd43",
      "listId": "9fc6ad7d-902a-4834-b161-a4911b883d44",
      "level": 1,
      "lists": [
        {
          "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
          "hasChildren": true
        }
      ],
      "isDeleted": true
    }
  ],
  "links": [
    {
      "href": "string",
      "rel": "string"
    }
  ],
  "page": {
    "number": 1,
    "size": 100,
    "totalElements": 1,
    "totalPages": 1
  }
}

```

PagedResourcesListItem

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|content|[[ListItem](#schemalistitem)]|false|none|none|
|links|[[Link](#schemalink)]|false|none|none|
|page|[PageMetadata](#schemapagemetadata)|false|none|none|

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

