<!-- Generator: Widdershins v4.0.1 -->

<h1 id="identity-apis">Identity APIs v4</h1>

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

Identity APIs

Base URLs:

* <a href="https://us.api.concursolutions.com/profile/identity/">https://us.api.concursolutions.com/profile/identity/</a>

<a href="http://us.api.concursolutions.com/terms">Terms of service</a>
Email: <a href="mailto:profile@concur.com">Support</a> 
License: <a href="https://developer.concur.com/Terms-of-Use.html">Concur</a>

<h1 id="identity-apis-user">User</h1>

## put__v4_Users_{id}_

> Code samples

```shell
# You can also use wget
curl -X PUT https://us.api.concursolutions.com/profile/identity/v4/Users/{id}/ \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
PUT https://us.api.concursolutions.com/profile/identity/v4/Users/{id}/ HTTP/1.1
Host: us.api.concursolutions.com
Content-Type: application/json
Accept: application/json

```

```javascript
const inputBody = '{
  "active": true,
  "addresses": [
    {
      "country": "string",
      "locality": "string",
      "postalCode": "string",
      "region": "string",
      "streetAddress": "string",
      "type": "work"
    }
  ],
  "dateOfBirth": "string",
  "displayName": "string",
  "emails": [
    {
      "dateAdded": "string",
      "dateVerified": "string",
      "notifications": true,
      "type": "work",
      "value": "string",
      "verified": true
    }
  ],
  "emergencyContacts": [
    {
      "country": "string",
      "emails": [
        "string"
      ],
      "locality": "string",
      "name": "string",
      "phones": [
        "string"
      ],
      "postalCode": "string",
      "region": "string",
      "relationship": "Spouse",
      "streetAddress": "string"
    }
  ],
  "entitlements": [
    "Expense"
  ],
  "externalId": "string",
  "gender": "Male",
  "id": "string",
  "localeOverrides": {
    "preference24Hour": "h:mm AM/PM",
    "preferenceCurrencySymbolLocation": "BeforeAmount",
    "preferenceDateFormat": "mm/dd/yyyy",
    "preferenceDefaultCalView": "day",
    "preferenceDistance": "mile",
    "preferenceEndDayViewHour": 0,
    "preferenceFirstDayOfWeek": "Monday",
    "preferenceHourMinuteSeparator": ":",
    "preferenceNegativeCurrencyFormat": "-100",
    "preferenceNegativeNumberFormat": "-100",
    "preferenceNumberFormat": "1,000.00",
    "preferenceStartDayViewHour": 0
  },
  "meta": {},
  "name": {
    "academicTitle": [
      "Dr."
    ],
    "familyName": "string",
    "familyNamePrefix": "string",
    "formatted": "string",
    "givenName": "string",
    "hasNoMiddleName": true,
    "honorificPrefix": "Miss",
    "honorificSuffix": "Jr.",
    "legalName": "string",
    "middleInitial": "string",
    "middleName": "string"
  },
  "nickName": "string",
  "phoneNumbers": [
    {
      "display": "string",
      "notifications": true,
      "operatingSystem": "Android Phone",
      "primary": true,
      "type": "work",
      "value": "string"
    }
  ],
  "preferredLanguage": "string",
  "schemas": [
    "urn:ietf:params:scim:schemas:core:2.0:User"
  ],
  "timezone": "string",
  "title": "string",
  "urn:ietf:params:scim:schemas:extension:enterprise:2.0:User": {
    "companyId": "string",
    "costCenter": "string",
    "department": "string",
    "division": "string",
    "employeeNumber": "string",
    "manager": {
      "$ref": "string",
      "displayName": "string",
      "employeeNumber": "string",
      "value": "string"
    },
    "orgUnit": "string",
    "organization": "string",
    "self": {
      "$ref": "string",
      "displayName": "string",
      "employeeNumber": "string",
      "value": "string"
    },
    "startDate": "string",
    "terminationDate": "string"
  },
  "userName": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'
};

fetch('https://us.api.concursolutions.com/profile/identity/v4/Users/{id}/',
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
  'Accept' => 'application/json'
}

result = RestClient.put 'https://us.api.concursolutions.com/profile/identity/v4/Users/{id}/',
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

r = requests.put('https://us.api.concursolutions.com/profile/identity/v4/Users/{id}/', headers = headers)

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
    $response = $client->request('PUT','https://us.api.concursolutions.com/profile/identity/v4/Users/{id}/', array(
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
URL obj = new URL("https://us.api.concursolutions.com/profile/identity/v4/Users/{id}/");
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
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PUT", "https://us.api.concursolutions.com/profile/identity/v4/Users/{id}/", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PUT /v4/Users/{id}/`

*Replace User Identity*

> Body parameter

```json
{
  "active": true,
  "addresses": [
    {
      "country": "string",
      "locality": "string",
      "postalCode": "string",
      "region": "string",
      "streetAddress": "string",
      "type": "work"
    }
  ],
  "dateOfBirth": "string",
  "displayName": "string",
  "emails": [
    {
      "dateAdded": "string",
      "dateVerified": "string",
      "notifications": true,
      "type": "work",
      "value": "string",
      "verified": true
    }
  ],
  "emergencyContacts": [
    {
      "country": "string",
      "emails": [
        "string"
      ],
      "locality": "string",
      "name": "string",
      "phones": [
        "string"
      ],
      "postalCode": "string",
      "region": "string",
      "relationship": "Spouse",
      "streetAddress": "string"
    }
  ],
  "entitlements": [
    "Expense"
  ],
  "externalId": "string",
  "gender": "Male",
  "id": "string",
  "localeOverrides": {
    "preference24Hour": "h:mm AM/PM",
    "preferenceCurrencySymbolLocation": "BeforeAmount",
    "preferenceDateFormat": "mm/dd/yyyy",
    "preferenceDefaultCalView": "day",
    "preferenceDistance": "mile",
    "preferenceEndDayViewHour": 0,
    "preferenceFirstDayOfWeek": "Monday",
    "preferenceHourMinuteSeparator": ":",
    "preferenceNegativeCurrencyFormat": "-100",
    "preferenceNegativeNumberFormat": "-100",
    "preferenceNumberFormat": "1,000.00",
    "preferenceStartDayViewHour": 0
  },
  "meta": {},
  "name": {
    "academicTitle": [
      "Dr."
    ],
    "familyName": "string",
    "familyNamePrefix": "string",
    "formatted": "string",
    "givenName": "string",
    "hasNoMiddleName": true,
    "honorificPrefix": "Miss",
    "honorificSuffix": "Jr.",
    "legalName": "string",
    "middleInitial": "string",
    "middleName": "string"
  },
  "nickName": "string",
  "phoneNumbers": [
    {
      "display": "string",
      "notifications": true,
      "operatingSystem": "Android Phone",
      "primary": true,
      "type": "work",
      "value": "string"
    }
  ],
  "preferredLanguage": "string",
  "schemas": [
    "urn:ietf:params:scim:schemas:core:2.0:User"
  ],
  "timezone": "string",
  "title": "string",
  "urn:ietf:params:scim:schemas:extension:enterprise:2.0:User": {
    "companyId": "string",
    "costCenter": "string",
    "department": "string",
    "division": "string",
    "employeeNumber": "string",
    "manager": {
      "$ref": "string",
      "displayName": "string",
      "employeeNumber": "string",
      "value": "string"
    },
    "orgUnit": "string",
    "organization": "string",
    "self": {
      "$ref": "string",
      "displayName": "string",
      "employeeNumber": "string",
      "value": "string"
    },
    "startDate": "string",
    "terminationDate": "string"
  },
  "userName": "string"
}
```

<h3 id="put__v4_users_{id}_-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|user's uuid|
|body|body|[User](#schemauser)|true|the user identity to update|

> Example responses

> 200 Response

```json
{
  "active": true,
  "addresses": [
    {
      "country": "string",
      "locality": "string",
      "postalCode": "string",
      "region": "string",
      "streetAddress": "string",
      "type": "work"
    }
  ],
  "dateOfBirth": "string",
  "displayName": "string",
  "emails": [
    {
      "dateAdded": "string",
      "dateVerified": "string",
      "notifications": true,
      "type": "work",
      "value": "string",
      "verified": true
    }
  ],
  "emergencyContacts": [
    {
      "country": "string",
      "emails": [
        "string"
      ],
      "locality": "string",
      "name": "string",
      "phones": [
        "string"
      ],
      "postalCode": "string",
      "region": "string",
      "relationship": "Spouse",
      "streetAddress": "string"
    }
  ],
  "entitlements": [
    "Expense"
  ],
  "externalId": "string",
  "gender": "Male",
  "id": "string",
  "localeOverrides": {
    "preference24Hour": "h:mm AM/PM",
    "preferenceCurrencySymbolLocation": "BeforeAmount",
    "preferenceDateFormat": "mm/dd/yyyy",
    "preferenceDefaultCalView": "day",
    "preferenceDistance": "mile",
    "preferenceEndDayViewHour": 0,
    "preferenceFirstDayOfWeek": "Monday",
    "preferenceHourMinuteSeparator": ":",
    "preferenceNegativeCurrencyFormat": "-100",
    "preferenceNegativeNumberFormat": "-100",
    "preferenceNumberFormat": "1,000.00",
    "preferenceStartDayViewHour": 0
  },
  "meta": {},
  "name": {
    "academicTitle": [
      "Dr."
    ],
    "familyName": "string",
    "familyNamePrefix": "string",
    "formatted": "string",
    "givenName": "string",
    "hasNoMiddleName": true,
    "honorificPrefix": "Miss",
    "honorificSuffix": "Jr.",
    "legalName": "string",
    "middleInitial": "string",
    "middleName": "string"
  },
  "nickName": "string",
  "phoneNumbers": [
    {
      "display": "string",
      "notifications": true,
      "operatingSystem": "Android Phone",
      "primary": true,
      "type": "work",
      "value": "string"
    }
  ],
  "preferredLanguage": "string",
  "schemas": [
    "urn:ietf:params:scim:schemas:core:2.0:User"
  ],
  "timezone": "string",
  "title": "string",
  "urn:ietf:params:scim:schemas:extension:enterprise:2.0:User": {
    "companyId": "string",
    "costCenter": "string",
    "department": "string",
    "division": "string",
    "employeeNumber": "string",
    "manager": {
      "$ref": "string",
      "displayName": "string",
      "employeeNumber": "string",
      "value": "string"
    },
    "orgUnit": "string",
    "organization": "string",
    "self": {
      "$ref": "string",
      "displayName": "string",
      "employeeNumber": "string",
      "value": "string"
    },
    "startDate": "string",
    "terminationDate": "string"
  },
  "userName": "string"
}
```

<h3 id="put__v4_users_{id}_-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful updation of user identity|[User](#schemauser)|
|default|Default|error updating user identity|[ErrorResponse](#schemaerrorresponse)|

<aside class="success">
This operation does not require authentication
</aside>

## get__v4_Users_{id}_

> Code samples

```shell
# You can also use wget
curl -X GET https://us.api.concursolutions.com/profile/identity/v4/Users/{id}/ \
  -H 'Accept: application/json'

```

```http
GET https://us.api.concursolutions.com/profile/identity/v4/Users/{id}/ HTTP/1.1
Host: us.api.concursolutions.com
Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('https://us.api.concursolutions.com/profile/identity/v4/Users/{id}/',
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

result = RestClient.get 'https://us.api.concursolutions.com/profile/identity/v4/Users/{id}/',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://us.api.concursolutions.com/profile/identity/v4/Users/{id}/', headers = headers)

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
    $response = $client->request('GET','https://us.api.concursolutions.com/profile/identity/v4/Users/{id}/', array(
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
URL obj = new URL("https://us.api.concursolutions.com/profile/identity/v4/Users/{id}/");
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
    req, err := http.NewRequest("GET", "https://us.api.concursolutions.com/profile/identity/v4/Users/{id}/", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /v4/Users/{id}/`

*Fetch User Identity*

<h3 id="get__v4_users_{id}_-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|user's uuid|

> Example responses

> 200 Response

```json
{
  "active": true,
  "addresses": [
    {
      "country": "string",
      "locality": "string",
      "postalCode": "string",
      "region": "string",
      "streetAddress": "string",
      "type": "work"
    }
  ],
  "dateOfBirth": "string",
  "displayName": "string",
  "emails": [
    {
      "dateAdded": "string",
      "dateVerified": "string",
      "notifications": true,
      "type": "work",
      "value": "string",
      "verified": true
    }
  ],
  "emergencyContacts": [
    {
      "country": "string",
      "emails": [
        "string"
      ],
      "locality": "string",
      "name": "string",
      "phones": [
        "string"
      ],
      "postalCode": "string",
      "region": "string",
      "relationship": "Spouse",
      "streetAddress": "string"
    }
  ],
  "entitlements": [
    "Expense"
  ],
  "externalId": "string",
  "gender": "Male",
  "id": "string",
  "localeOverrides": {
    "preference24Hour": "h:mm AM/PM",
    "preferenceCurrencySymbolLocation": "BeforeAmount",
    "preferenceDateFormat": "mm/dd/yyyy",
    "preferenceDefaultCalView": "day",
    "preferenceDistance": "mile",
    "preferenceEndDayViewHour": 0,
    "preferenceFirstDayOfWeek": "Monday",
    "preferenceHourMinuteSeparator": ":",
    "preferenceNegativeCurrencyFormat": "-100",
    "preferenceNegativeNumberFormat": "-100",
    "preferenceNumberFormat": "1,000.00",
    "preferenceStartDayViewHour": 0
  },
  "meta": {},
  "name": {
    "academicTitle": [
      "Dr."
    ],
    "familyName": "string",
    "familyNamePrefix": "string",
    "formatted": "string",
    "givenName": "string",
    "hasNoMiddleName": true,
    "honorificPrefix": "Miss",
    "honorificSuffix": "Jr.",
    "legalName": "string",
    "middleInitial": "string",
    "middleName": "string"
  },
  "nickName": "string",
  "phoneNumbers": [
    {
      "display": "string",
      "notifications": true,
      "operatingSystem": "Android Phone",
      "primary": true,
      "type": "work",
      "value": "string"
    }
  ],
  "preferredLanguage": "string",
  "schemas": [
    "urn:ietf:params:scim:schemas:core:2.0:User"
  ],
  "timezone": "string",
  "title": "string",
  "urn:ietf:params:scim:schemas:extension:enterprise:2.0:User": {
    "companyId": "string",
    "costCenter": "string",
    "department": "string",
    "division": "string",
    "employeeNumber": "string",
    "manager": {
      "$ref": "string",
      "displayName": "string",
      "employeeNumber": "string",
      "value": "string"
    },
    "orgUnit": "string",
    "organization": "string",
    "self": {
      "$ref": "string",
      "displayName": "string",
      "employeeNumber": "string",
      "value": "string"
    },
    "startDate": "string",
    "terminationDate": "string"
  },
  "userName": "string"
}
```

<h3 id="get__v4_users_{id}_-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successfully fetched User Identity|[User](#schemauser)|
|default|Default|error fetching user identity|[ErrorResponse](#schemaerrorresponse)|

<aside class="success">
This operation does not require authentication
</aside>

## patch__v4_Users_{id}_

> Code samples

```shell
# You can also use wget
curl -X PATCH https://us.api.concursolutions.com/profile/identity/v4/Users/{id}/ \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
PATCH https://us.api.concursolutions.com/profile/identity/v4/Users/{id}/ HTTP/1.1
Host: us.api.concursolutions.com
Content-Type: application/json
Accept: application/json

```

```javascript
const inputBody = '{}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'
};

fetch('https://us.api.concursolutions.com/profile/identity/v4/Users/{id}/',
{
  method: 'PATCH',
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

result = RestClient.patch 'https://us.api.concursolutions.com/profile/identity/v4/Users/{id}/',
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

r = requests.patch('https://us.api.concursolutions.com/profile/identity/v4/Users/{id}/', headers = headers)

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
    $response = $client->request('PATCH','https://us.api.concursolutions.com/profile/identity/v4/Users/{id}/', array(
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
URL obj = new URL("https://us.api.concursolutions.com/profile/identity/v4/Users/{id}/");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PATCH");
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
    req, err := http.NewRequest("PATCH", "https://us.api.concursolutions.com/profile/identity/v4/Users/{id}/", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PATCH /v4/Users/{id}/`

*Patch User Identity*

> Body parameter

```json
{}
```

<h3 id="patch__v4_users_{id}_-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|user's uuid|
|body|body|object|true|patch operations to apply on the user identity|

> Example responses

> 200 Response

```json
{
  "active": true,
  "addresses": [
    {
      "country": "string",
      "locality": "string",
      "postalCode": "string",
      "region": "string",
      "streetAddress": "string",
      "type": "work"
    }
  ],
  "dateOfBirth": "string",
  "displayName": "string",
  "emails": [
    {
      "dateAdded": "string",
      "dateVerified": "string",
      "notifications": true,
      "type": "work",
      "value": "string",
      "verified": true
    }
  ],
  "emergencyContacts": [
    {
      "country": "string",
      "emails": [
        "string"
      ],
      "locality": "string",
      "name": "string",
      "phones": [
        "string"
      ],
      "postalCode": "string",
      "region": "string",
      "relationship": "Spouse",
      "streetAddress": "string"
    }
  ],
  "entitlements": [
    "Expense"
  ],
  "externalId": "string",
  "gender": "Male",
  "id": "string",
  "localeOverrides": {
    "preference24Hour": "h:mm AM/PM",
    "preferenceCurrencySymbolLocation": "BeforeAmount",
    "preferenceDateFormat": "mm/dd/yyyy",
    "preferenceDefaultCalView": "day",
    "preferenceDistance": "mile",
    "preferenceEndDayViewHour": 0,
    "preferenceFirstDayOfWeek": "Monday",
    "preferenceHourMinuteSeparator": ":",
    "preferenceNegativeCurrencyFormat": "-100",
    "preferenceNegativeNumberFormat": "-100",
    "preferenceNumberFormat": "1,000.00",
    "preferenceStartDayViewHour": 0
  },
  "meta": {},
  "name": {
    "academicTitle": [
      "Dr."
    ],
    "familyName": "string",
    "familyNamePrefix": "string",
    "formatted": "string",
    "givenName": "string",
    "hasNoMiddleName": true,
    "honorificPrefix": "Miss",
    "honorificSuffix": "Jr.",
    "legalName": "string",
    "middleInitial": "string",
    "middleName": "string"
  },
  "nickName": "string",
  "phoneNumbers": [
    {
      "display": "string",
      "notifications": true,
      "operatingSystem": "Android Phone",
      "primary": true,
      "type": "work",
      "value": "string"
    }
  ],
  "preferredLanguage": "string",
  "schemas": [
    "urn:ietf:params:scim:schemas:core:2.0:User"
  ],
  "timezone": "string",
  "title": "string",
  "urn:ietf:params:scim:schemas:extension:enterprise:2.0:User": {
    "companyId": "string",
    "costCenter": "string",
    "department": "string",
    "division": "string",
    "employeeNumber": "string",
    "manager": {
      "$ref": "string",
      "displayName": "string",
      "employeeNumber": "string",
      "value": "string"
    },
    "orgUnit": "string",
    "organization": "string",
    "self": {
      "$ref": "string",
      "displayName": "string",
      "employeeNumber": "string",
      "value": "string"
    },
    "startDate": "string",
    "terminationDate": "string"
  },
  "userName": "string"
}
```

<h3 id="patch__v4_users_{id}_-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successfully patched User Identity|[User](#schemauser)|
|default|Default|Error patching user identity|[ErrorResponse](#schemaerrorresponse)|

<aside class="success">
This operation does not require authentication
</aside>

## post__v4_Users

> Code samples

```shell
# You can also use wget
curl -X POST https://us.api.concursolutions.com/profile/identity/v4/Users \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
POST https://us.api.concursolutions.com/profile/identity/v4/Users HTTP/1.1
Host: us.api.concursolutions.com
Content-Type: application/json
Accept: application/json

```

```javascript
const inputBody = '{
  "active": true,
  "addresses": [
    {
      "country": "string",
      "locality": "string",
      "postalCode": "string",
      "region": "string",
      "streetAddress": "string",
      "type": "work"
    }
  ],
  "dateOfBirth": "string",
  "displayName": "string",
  "emails": [
    {
      "dateAdded": "string",
      "dateVerified": "string",
      "notifications": true,
      "type": "work",
      "value": "string",
      "verified": true
    }
  ],
  "emergencyContacts": [
    {
      "country": "string",
      "emails": [
        "string"
      ],
      "locality": "string",
      "name": "string",
      "phones": [
        "string"
      ],
      "postalCode": "string",
      "region": "string",
      "relationship": "Spouse",
      "streetAddress": "string"
    }
  ],
  "entitlements": [
    "Expense"
  ],
  "externalId": "string",
  "gender": "Male",
  "id": "string",
  "localeOverrides": {
    "preference24Hour": "h:mm AM/PM",
    "preferenceCurrencySymbolLocation": "BeforeAmount",
    "preferenceDateFormat": "mm/dd/yyyy",
    "preferenceDefaultCalView": "day",
    "preferenceDistance": "mile",
    "preferenceEndDayViewHour": 0,
    "preferenceFirstDayOfWeek": "Monday",
    "preferenceHourMinuteSeparator": ":",
    "preferenceNegativeCurrencyFormat": "-100",
    "preferenceNegativeNumberFormat": "-100",
    "preferenceNumberFormat": "1,000.00",
    "preferenceStartDayViewHour": 0
  },
  "meta": {},
  "name": {
    "academicTitle": [
      "Dr."
    ],
    "familyName": "string",
    "familyNamePrefix": "string",
    "formatted": "string",
    "givenName": "string",
    "hasNoMiddleName": true,
    "honorificPrefix": "Miss",
    "honorificSuffix": "Jr.",
    "legalName": "string",
    "middleInitial": "string",
    "middleName": "string"
  },
  "nickName": "string",
  "phoneNumbers": [
    {
      "display": "string",
      "notifications": true,
      "operatingSystem": "Android Phone",
      "primary": true,
      "type": "work",
      "value": "string"
    }
  ],
  "preferredLanguage": "string",
  "schemas": [
    "urn:ietf:params:scim:schemas:core:2.0:User"
  ],
  "timezone": "string",
  "title": "string",
  "urn:ietf:params:scim:schemas:extension:enterprise:2.0:User": {
    "companyId": "string",
    "costCenter": "string",
    "department": "string",
    "division": "string",
    "employeeNumber": "string",
    "manager": {
      "$ref": "string",
      "displayName": "string",
      "employeeNumber": "string",
      "value": "string"
    },
    "orgUnit": "string",
    "organization": "string",
    "self": {
      "$ref": "string",
      "displayName": "string",
      "employeeNumber": "string",
      "value": "string"
    },
    "startDate": "string",
    "terminationDate": "string"
  },
  "userName": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'
};

fetch('https://us.api.concursolutions.com/profile/identity/v4/Users',
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

result = RestClient.post 'https://us.api.concursolutions.com/profile/identity/v4/Users',
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

r = requests.post('https://us.api.concursolutions.com/profile/identity/v4/Users', headers = headers)

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
    $response = $client->request('POST','https://us.api.concursolutions.com/profile/identity/v4/Users', array(
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
URL obj = new URL("https://us.api.concursolutions.com/profile/identity/v4/Users");
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
    req, err := http.NewRequest("POST", "https://us.api.concursolutions.com/profile/identity/v4/Users", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /v4/Users`

*Create User Identity*

> Body parameter

```json
{
  "active": true,
  "addresses": [
    {
      "country": "string",
      "locality": "string",
      "postalCode": "string",
      "region": "string",
      "streetAddress": "string",
      "type": "work"
    }
  ],
  "dateOfBirth": "string",
  "displayName": "string",
  "emails": [
    {
      "dateAdded": "string",
      "dateVerified": "string",
      "notifications": true,
      "type": "work",
      "value": "string",
      "verified": true
    }
  ],
  "emergencyContacts": [
    {
      "country": "string",
      "emails": [
        "string"
      ],
      "locality": "string",
      "name": "string",
      "phones": [
        "string"
      ],
      "postalCode": "string",
      "region": "string",
      "relationship": "Spouse",
      "streetAddress": "string"
    }
  ],
  "entitlements": [
    "Expense"
  ],
  "externalId": "string",
  "gender": "Male",
  "id": "string",
  "localeOverrides": {
    "preference24Hour": "h:mm AM/PM",
    "preferenceCurrencySymbolLocation": "BeforeAmount",
    "preferenceDateFormat": "mm/dd/yyyy",
    "preferenceDefaultCalView": "day",
    "preferenceDistance": "mile",
    "preferenceEndDayViewHour": 0,
    "preferenceFirstDayOfWeek": "Monday",
    "preferenceHourMinuteSeparator": ":",
    "preferenceNegativeCurrencyFormat": "-100",
    "preferenceNegativeNumberFormat": "-100",
    "preferenceNumberFormat": "1,000.00",
    "preferenceStartDayViewHour": 0
  },
  "meta": {},
  "name": {
    "academicTitle": [
      "Dr."
    ],
    "familyName": "string",
    "familyNamePrefix": "string",
    "formatted": "string",
    "givenName": "string",
    "hasNoMiddleName": true,
    "honorificPrefix": "Miss",
    "honorificSuffix": "Jr.",
    "legalName": "string",
    "middleInitial": "string",
    "middleName": "string"
  },
  "nickName": "string",
  "phoneNumbers": [
    {
      "display": "string",
      "notifications": true,
      "operatingSystem": "Android Phone",
      "primary": true,
      "type": "work",
      "value": "string"
    }
  ],
  "preferredLanguage": "string",
  "schemas": [
    "urn:ietf:params:scim:schemas:core:2.0:User"
  ],
  "timezone": "string",
  "title": "string",
  "urn:ietf:params:scim:schemas:extension:enterprise:2.0:User": {
    "companyId": "string",
    "costCenter": "string",
    "department": "string",
    "division": "string",
    "employeeNumber": "string",
    "manager": {
      "$ref": "string",
      "displayName": "string",
      "employeeNumber": "string",
      "value": "string"
    },
    "orgUnit": "string",
    "organization": "string",
    "self": {
      "$ref": "string",
      "displayName": "string",
      "employeeNumber": "string",
      "value": "string"
    },
    "startDate": "string",
    "terminationDate": "string"
  },
  "userName": "string"
}
```

<h3 id="post__v4_users-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[User](#schemauser)|true|the user identity to create|

> Example responses

> 200 Response

```json
{
  "active": true,
  "addresses": [
    {
      "country": "string",
      "locality": "string",
      "postalCode": "string",
      "region": "string",
      "streetAddress": "string",
      "type": "work"
    }
  ],
  "dateOfBirth": "string",
  "displayName": "string",
  "emails": [
    {
      "dateAdded": "string",
      "dateVerified": "string",
      "notifications": true,
      "type": "work",
      "value": "string",
      "verified": true
    }
  ],
  "emergencyContacts": [
    {
      "country": "string",
      "emails": [
        "string"
      ],
      "locality": "string",
      "name": "string",
      "phones": [
        "string"
      ],
      "postalCode": "string",
      "region": "string",
      "relationship": "Spouse",
      "streetAddress": "string"
    }
  ],
  "entitlements": [
    "Expense"
  ],
  "externalId": "string",
  "gender": "Male",
  "id": "string",
  "localeOverrides": {
    "preference24Hour": "h:mm AM/PM",
    "preferenceCurrencySymbolLocation": "BeforeAmount",
    "preferenceDateFormat": "mm/dd/yyyy",
    "preferenceDefaultCalView": "day",
    "preferenceDistance": "mile",
    "preferenceEndDayViewHour": 0,
    "preferenceFirstDayOfWeek": "Monday",
    "preferenceHourMinuteSeparator": ":",
    "preferenceNegativeCurrencyFormat": "-100",
    "preferenceNegativeNumberFormat": "-100",
    "preferenceNumberFormat": "1,000.00",
    "preferenceStartDayViewHour": 0
  },
  "meta": {},
  "name": {
    "academicTitle": [
      "Dr."
    ],
    "familyName": "string",
    "familyNamePrefix": "string",
    "formatted": "string",
    "givenName": "string",
    "hasNoMiddleName": true,
    "honorificPrefix": "Miss",
    "honorificSuffix": "Jr.",
    "legalName": "string",
    "middleInitial": "string",
    "middleName": "string"
  },
  "nickName": "string",
  "phoneNumbers": [
    {
      "display": "string",
      "notifications": true,
      "operatingSystem": "Android Phone",
      "primary": true,
      "type": "work",
      "value": "string"
    }
  ],
  "preferredLanguage": "string",
  "schemas": [
    "urn:ietf:params:scim:schemas:core:2.0:User"
  ],
  "timezone": "string",
  "title": "string",
  "urn:ietf:params:scim:schemas:extension:enterprise:2.0:User": {
    "companyId": "string",
    "costCenter": "string",
    "department": "string",
    "division": "string",
    "employeeNumber": "string",
    "manager": {
      "$ref": "string",
      "displayName": "string",
      "employeeNumber": "string",
      "value": "string"
    },
    "orgUnit": "string",
    "organization": "string",
    "self": {
      "$ref": "string",
      "displayName": "string",
      "employeeNumber": "string",
      "value": "string"
    },
    "startDate": "string",
    "terminationDate": "string"
  },
  "userName": "string"
}
```

<h3 id="post__v4_users-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|created User Identity|[User](#schemauser)|
|default|Default|error creating user identity|[ErrorResponse](#schemaerrorresponse)|

<aside class="success">
This operation does not require authentication
</aside>

## get__v4_Users

> Code samples

```shell
# You can also use wget
curl -X GET https://us.api.concursolutions.com/profile/identity/v4/Users \
  -H 'Accept: application/json'

```

```http
GET https://us.api.concursolutions.com/profile/identity/v4/Users HTTP/1.1
Host: us.api.concursolutions.com
Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('https://us.api.concursolutions.com/profile/identity/v4/Users',
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

result = RestClient.get 'https://us.api.concursolutions.com/profile/identity/v4/Users',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://us.api.concursolutions.com/profile/identity/v4/Users', headers = headers)

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
    $response = $client->request('GET','https://us.api.concursolutions.com/profile/identity/v4/Users', array(
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
URL obj = new URL("https://us.api.concursolutions.com/profile/identity/v4/Users");
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
    req, err := http.NewRequest("GET", "https://us.api.concursolutions.com/profile/identity/v4/Users", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /v4/Users`

*Lookup User(s) for Company*

<h3 id="get__v4_users-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|filter|query|string|false|The filter string used to request a subset of resources|
|attributes|query|string|false|A multi-valued list of strings indicating the names of resource attributes to return in the response|
|excludedAttributes|query|string|false|A multi-valued list of strings indicating the names of resource attributes to be removed from the default set of attributes to return|
|startIndex|query|integer|false|The 1-based index of the first query result|
|count|query|integer|false|The desired maximum number of query results per page|

> Example responses

> 200 Response

```json
{
  "totalResults": 0,
  "itemsPerPage": 0,
  "startIndex": 0,
  "schemas": [
    "urn:ietf:params:scim:api:messages:2.0:ListResponse"
  ],
  "Resources": [
    {
      "active": true,
      "addresses": [
        {
          "country": "string",
          "locality": "string",
          "postalCode": "string",
          "region": "string",
          "streetAddress": "string",
          "type": "work"
        }
      ],
      "dateOfBirth": "string",
      "displayName": "string",
      "emails": [
        {
          "dateAdded": "string",
          "dateVerified": "string",
          "notifications": true,
          "type": "work",
          "value": "string",
          "verified": true
        }
      ],
      "emergencyContacts": [
        {
          "country": "string",
          "emails": [
            "string"
          ],
          "locality": "string",
          "name": "string",
          "phones": [
            "string"
          ],
          "postalCode": "string",
          "region": "string",
          "relationship": "Spouse",
          "streetAddress": "string"
        }
      ],
      "entitlements": [
        "Expense"
      ],
      "externalId": "string",
      "gender": "Male",
      "id": "string",
      "localeOverrides": {
        "preference24Hour": "h:mm AM/PM",
        "preferenceCurrencySymbolLocation": "BeforeAmount",
        "preferenceDateFormat": "mm/dd/yyyy",
        "preferenceDefaultCalView": "day",
        "preferenceDistance": "mile",
        "preferenceEndDayViewHour": 0,
        "preferenceFirstDayOfWeek": "Monday",
        "preferenceHourMinuteSeparator": ":",
        "preferenceNegativeCurrencyFormat": "-100",
        "preferenceNegativeNumberFormat": "-100",
        "preferenceNumberFormat": "1,000.00",
        "preferenceStartDayViewHour": 0
      },
      "meta": {},
      "name": {
        "academicTitle": [
          "Dr."
        ],
        "familyName": "string",
        "familyNamePrefix": "string",
        "formatted": "string",
        "givenName": "string",
        "hasNoMiddleName": true,
        "honorificPrefix": "Miss",
        "honorificSuffix": "Jr.",
        "legalName": "string",
        "middleInitial": "string",
        "middleName": "string"
      },
      "nickName": "string",
      "phoneNumbers": [
        {
          "display": "string",
          "notifications": true,
          "operatingSystem": "Android Phone",
          "primary": true,
          "type": "work",
          "value": "string"
        }
      ],
      "preferredLanguage": "string",
      "schemas": [
        "urn:ietf:params:scim:schemas:core:2.0:User"
      ],
      "timezone": "string",
      "title": "string",
      "urn:ietf:params:scim:schemas:extension:enterprise:2.0:User": {
        "companyId": "string",
        "costCenter": "string",
        "department": "string",
        "division": "string",
        "employeeNumber": "string",
        "manager": {
          "$ref": "string",
          "displayName": "string",
          "employeeNumber": "string",
          "value": "string"
        },
        "orgUnit": "string",
        "organization": "string",
        "self": {
          "$ref": "string",
          "displayName": "string",
          "employeeNumber": "string",
          "value": "string"
        },
        "startDate": "string",
        "terminationDate": "string"
      },
      "userName": "string"
    }
  ]
}
```

<h3 id="get__v4_users-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successfully fetched user identities|[UserList](#schemauserlist)|
|default|Default|Error fetching user identity|[ErrorResponse](#schemaerrorresponse)|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="identity-apis-schema">Schema</h1>

## get__v4_Schemas_

> Code samples

```shell
# You can also use wget
curl -X GET https://us.api.concursolutions.com/profile/identity/v4/Schemas/ \
  -H 'Accept: application/json'

```

```http
GET https://us.api.concursolutions.com/profile/identity/v4/Schemas/ HTTP/1.1
Host: us.api.concursolutions.com
Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('https://us.api.concursolutions.com/profile/identity/v4/Schemas/',
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

result = RestClient.get 'https://us.api.concursolutions.com/profile/identity/v4/Schemas/',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://us.api.concursolutions.com/profile/identity/v4/Schemas/', headers = headers)

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
    $response = $client->request('GET','https://us.api.concursolutions.com/profile/identity/v4/Schemas/', array(
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
URL obj = new URL("https://us.api.concursolutions.com/profile/identity/v4/Schemas/");
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
    req, err := http.NewRequest("GET", "https://us.api.concursolutions.com/profile/identity/v4/Schemas/", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /v4/Schemas/`

*Get all schemas*

> Example responses

> default Response

```json
{
  "scimType": "string",
  "detail": "string",
  "status": "string",
  "urn:ietf:params:scim:api:messages:concur:2.0:Error": {
    "messages": [
      {
        "code": "string",
        "message": "string",
        "schemaPath": "string",
        "type": "error"
      }
    ]
  }
}
```

<h3 id="get__v4_schemas_-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|All supported schemas|None|
|default|Default|error fetching schemas|[ErrorResponse](#schemaerrorresponse)|

<aside class="success">
This operation does not require authentication
</aside>

## get__v4_Schemas_{id}

> Code samples

```shell
# You can also use wget
curl -X GET https://us.api.concursolutions.com/profile/identity/v4/Schemas/{id} \
  -H 'Accept: application/json'

```

```http
GET https://us.api.concursolutions.com/profile/identity/v4/Schemas/{id} HTTP/1.1
Host: us.api.concursolutions.com
Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('https://us.api.concursolutions.com/profile/identity/v4/Schemas/{id}',
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

result = RestClient.get 'https://us.api.concursolutions.com/profile/identity/v4/Schemas/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://us.api.concursolutions.com/profile/identity/v4/Schemas/{id}', headers = headers)

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
    $response = $client->request('GET','https://us.api.concursolutions.com/profile/identity/v4/Schemas/{id}', array(
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
URL obj = new URL("https://us.api.concursolutions.com/profile/identity/v4/Schemas/{id}");
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
    req, err := http.NewRequest("GET", "https://us.api.concursolutions.com/profile/identity/v4/Schemas/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /v4/Schemas/{id}`

*Get Schema*

<h3 id="get__v4_schemas_{id}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|schema id|

#### Enumerated Values

|Parameter|Value|
|---|---|
|id|com:concur:cte:user:2.0|
|id|com:concur:cte:company:2.0|

> Example responses

> default Response

```json
{
  "scimType": "string",
  "detail": "string",
  "status": "string",
  "urn:ietf:params:scim:api:messages:concur:2.0:Error": {
    "messages": [
      {
        "code": "string",
        "message": "string",
        "schemaPath": "string",
        "type": "error"
      }
    ]
  }
}
```

<h3 id="get__v4_schemas_{id}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successfully fetched schema|None|
|default|Default|error fetching schema|[ErrorResponse](#schemaerrorresponse)|

<aside class="success">
This operation does not require authentication
</aside>

## getServiceProviderConfig

<a id="opIdgetServiceProviderConfig"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://us.api.concursolutions.com/profile/identity/v4/ServiceProviderConfig \
  -H 'Accept: application/json'

```

```http
GET https://us.api.concursolutions.com/profile/identity/v4/ServiceProviderConfig HTTP/1.1
Host: us.api.concursolutions.com
Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('https://us.api.concursolutions.com/profile/identity/v4/ServiceProviderConfig',
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

result = RestClient.get 'https://us.api.concursolutions.com/profile/identity/v4/ServiceProviderConfig',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://us.api.concursolutions.com/profile/identity/v4/ServiceProviderConfig', headers = headers)

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
    $response = $client->request('GET','https://us.api.concursolutions.com/profile/identity/v4/ServiceProviderConfig', array(
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
URL obj = new URL("https://us.api.concursolutions.com/profile/identity/v4/ServiceProviderConfig");
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
    req, err := http.NewRequest("GET", "https://us.api.concursolutions.com/profile/identity/v4/ServiceProviderConfig", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /v4/ServiceProviderConfig`

*Get Service Provider Configurations*

Queries service provider configurations.

> Example responses

> 200 Response

```json
{
  "authenticationSchemes": {
    "description": "string",
    "documentationUrl": "string",
    "name": "string",
    "specUrl": "string"
  },
  "bulk": {
    "supported": true
  },
  "changePassword": {
    "supported": true
  },
  "documentationUrl": "string",
  "etag": {
    "supported": true
  },
  "filter": {
    "supported": true
  },
  "patch": {
    "supported": true
  },
  "sort": {
    "supported": true
  }
}
```

<h3 id="getserviceproviderconfig-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|The request has succeeded.|[ServiceProviderConfig](#schemaserviceproviderconfig)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Invalid token passed|None|
|502|[Bad Gateway](https://tools.ietf.org/html/rfc7231#section-6.6.3)|Authentication or account gateway error occurred|None|
|504|[Gateway Time-out](https://tools.ietf.org/html/rfc7231#section-6.6.5)|Authentication or account gateway timeout occurred|None|

<aside class="success">
This operation does not require authentication
</aside>

## getServiceProviderResourceTypes

<a id="opIdgetServiceProviderResourceTypes"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://us.api.concursolutions.com/profile/identity/v4/ResourceTypes \
  -H 'Accept: application/json'

```

```http
GET https://us.api.concursolutions.com/profile/identity/v4/ResourceTypes HTTP/1.1
Host: us.api.concursolutions.com
Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('https://us.api.concursolutions.com/profile/identity/v4/ResourceTypes',
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

result = RestClient.get 'https://us.api.concursolutions.com/profile/identity/v4/ResourceTypes',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://us.api.concursolutions.com/profile/identity/v4/ResourceTypes', headers = headers)

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
    $response = $client->request('GET','https://us.api.concursolutions.com/profile/identity/v4/ResourceTypes', array(
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
URL obj = new URL("https://us.api.concursolutions.com/profile/identity/v4/ResourceTypes");
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
    req, err := http.NewRequest("GET", "https://us.api.concursolutions.com/profile/identity/v4/ResourceTypes", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /v4/ResourceTypes`

*Get Service Provider Configurations*

Queries service provider resource types.

> Example responses

> 200 Response

```json
[
  {
    "active": true,
    "addresses": [
      {
        "country": "string",
        "locality": "string",
        "postalCode": "string",
        "region": "string",
        "streetAddress": "string",
        "type": "work"
      }
    ],
    "dateOfBirth": "string",
    "displayName": "string",
    "emails": [
      {
        "dateAdded": "string",
        "dateVerified": "string",
        "notifications": true,
        "type": "work",
        "value": "string",
        "verified": true
      }
    ],
    "emergencyContacts": [
      {
        "country": "string",
        "emails": [
          "string"
        ],
        "locality": "string",
        "name": "string",
        "phones": [
          "string"
        ],
        "postalCode": "string",
        "region": "string",
        "relationship": "Spouse",
        "streetAddress": "string"
      }
    ],
    "entitlements": [
      "Expense"
    ],
    "externalId": "string",
    "gender": "Male",
    "id": "string",
    "localeOverrides": {
      "preference24Hour": "h:mm AM/PM",
      "preferenceCurrencySymbolLocation": "BeforeAmount",
      "preferenceDateFormat": "mm/dd/yyyy",
      "preferenceDefaultCalView": "day",
      "preferenceDistance": "mile",
      "preferenceEndDayViewHour": 0,
      "preferenceFirstDayOfWeek": "Monday",
      "preferenceHourMinuteSeparator": ":",
      "preferenceNegativeCurrencyFormat": "-100",
      "preferenceNegativeNumberFormat": "-100",
      "preferenceNumberFormat": "1,000.00",
      "preferenceStartDayViewHour": 0
    },
    "meta": {},
    "name": {
      "academicTitle": [
        "Dr."
      ],
      "familyName": "string",
      "familyNamePrefix": "string",
      "formatted": "string",
      "givenName": "string",
      "hasNoMiddleName": true,
      "honorificPrefix": "Miss",
      "honorificSuffix": "Jr.",
      "legalName": "string",
      "middleInitial": "string",
      "middleName": "string"
    },
    "nickName": "string",
    "phoneNumbers": [
      {
        "display": "string",
        "notifications": true,
        "operatingSystem": "Android Phone",
        "primary": true,
        "type": "work",
        "value": "string"
      }
    ],
    "preferredLanguage": "string",
    "schemas": [
      "urn:ietf:params:scim:schemas:core:2.0:User"
    ],
    "timezone": "string",
    "title": "string",
    "urn:ietf:params:scim:schemas:extension:enterprise:2.0:User": {
      "companyId": "string",
      "costCenter": "string",
      "department": "string",
      "division": "string",
      "employeeNumber": "string",
      "manager": {
        "$ref": "string",
        "displayName": "string",
        "employeeNumber": "string",
        "value": "string"
      },
      "orgUnit": "string",
      "organization": "string",
      "self": {
        "$ref": "string",
        "displayName": "string",
        "employeeNumber": "string",
        "value": "string"
      },
      "startDate": "string",
      "terminationDate": "string"
    },
    "userName": "string"
  }
]
```

<h3 id="getserviceproviderresourcetypes-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|The request has succeeded.|Inline|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Invalid token passed|None|
|502|[Bad Gateway](https://tools.ietf.org/html/rfc7231#section-6.6.3)|Authentication or account gateway error occurred|None|
|504|[Gateway Time-out](https://tools.ietf.org/html/rfc7231#section-6.6.5)|Authentication or account gateway timeout occurred|None|

<h3 id="getserviceproviderresourcetypes-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[User](#schemauser)]|false|none|none|
|» active|boolean|true|none|A Boolean value indicating whether the User is active.|
|» addresses|[object]|false|none|A physical mailing address for this User. Canonical type values of 'work', 'home', and 'other'. This attribute is a complex type with the following sub-attributes.|
|»» country|string|false|none|A two-letter country code defined in ISO 3166-1 alpha-2|
|»» locality|string|false|none|The city or locality.|
|»» postalCode|string|false|none|The zip code or postal code.|
|»» region|string|false|none|The state or region.|
|»» streetAddress|string|false|none|The full street address component, which may include house number, street name, P.O. box, and multi-line extended street address information.  This attribute MAY contain newlines.|
|»» type|string|false|none|A label indicating the function of the address, e.g., 'work' or 'home'.|
|» dateOfBirth|string|false|none|The user's date of birth , in YYYY-MM-DD format|
|» displayName|string|false|none|The name of the User, suitable for display to end-users.|
|» emails|[object]|true|none|Email addresses for the user. The value SHOULD be canonicalized by the service provider, e.g., 'bjensen@example.com' instead of 'bjensen@EXAMPLE.COM'. Canonical type values of 'work', 'home', and 'other'.|
|»» dateAdded|string|false|none|The date and time the email was added to the user's profile.|
|»» dateVerified|string|false|none|The date and time the email was verified|
|»» notifications|boolean|false|none|Notifications opt-in for emails|
|»» type|string|false|none|A label indicating the attribute's function, e.g., 'Work' or 'Home'.|
|»» value|string|true|none|Email address value|
|»» verified|boolean|false|none|flag to note which email has been verified by the user.|
|» emergencyContacts|[object]|false|none|Emergency Contact information for the User.|
|»» country|string|false|none|A two-letter country code defined in ISO 3166-1 alpha-2|
|»» emails|[string]|false|none|Emails of the contact|
|»» locality|string|false|none|The city or locality.|
|»» name|string|true|none|Contact name.|
|»» phones|[string]|false|none|Phone numbers of the contact|
|»» postalCode|string|false|none|The zip code or postal code.|
|»» region|string|false|none|The state or region.|
|»» relationship|string|true|none|Emergency contact relationship.|
|»» streetAddress|string|false|none|The full street address component, which may include house number, street name, P.O. box, and multi-line extended street address information.  This attribute MAY contain newlines.|
|» entitlements|[string]|false|none|The features enabled for the user|
|» externalId|string|false|none|User identifier from the provisioning client|
|» gender|string|false|none|The user's gender|
|» id|string|true|none|Unique identifier for the user - a uuid|
|» localeOverrides|object|false|none|Support for users who want to override locale settings|
|»» preference24Hour|string|false|none|preferred 24 hour format for the user|
|»» preferenceCurrencySymbolLocation|string|false|none|preferred currency symbol location for the user|
|»» preferenceDateFormat|string|false|none|preferred date format for the user|
|»» preferenceDefaultCalView|string|false|none|preferred default calendar view for the user|
|»» preferenceDistance|string|false|none|preferred distance metric|
|»» preferenceEndDayViewHour|integer|false|none|preferred hour setting for the end of day, 0-23|
|»» preferenceFirstDayOfWeek|string|false|none|preferred first day of the week for the user|
|»» preferenceHourMinuteSeparator|string|false|none|preferred separator between hour and minute|
|»» preferenceNegativeCurrencyFormat|string|false|none|preferred negative currency format for the user|
|»» preferenceNegativeNumberFormat|string|false|none|preferred negative number format for the user|
|»» preferenceNumberFormat|string|false|none|preferred number format for the user|
|»» preferenceStartDayViewHour|integer|false|none|preferred start of day for the user, from 1|
|» meta|object|false|none|none|
|» name|object|true|none|The user's name|
|»» academicTitle|[string]|false|none|Title signifying level of academic achievement|
|»» familyName|string|true|none|The family name of the User, or last name in most Western languages (e.g., 'Jensen' given the full name 'Ms. Barbara J Jensen, III').|
|»» familyNamePrefix|string|false|none|The family name prefix of the User (e.g. 'van' given the full name 'Vincent van Gogh')|
|»» formatted|string|false|none|The full name, formatted for display (e.g., 'Jensen, Barbara Jane').|
|»» givenName|string|true|none|The given name of the User, or first name in most Western languages (e.g., 'Barbara' given the full name 'Ms. Barbara J Jensen, III').|
|»» hasNoMiddleName|boolean|false|none|A boolean indicating that the user does not have a middle name|
|»» honorificPrefix|string|false|none|The honorific prefix(es) of the User, or title in most Western languages (e.g., 'Ms.' given the full name 'Ms. Barbara J Jensen, III').|
|»» honorificSuffix|string|false|none|The honorific suffix(es) of the User, or  suffix in most Western languages (e.g., 'III' given the full name  'Ms. Barbara J Jensen, III').|
|»» legalName|string|false|none|The legal name of the User (e.g., 'Jane' given the full name 'Ms. Barbara J Jensen, III').|
|»» middleInitial|string|false|none|middle initial, if the user has a middle name|
|»» middleName|string|false|none|The middle name(s) of the User (e.g., 'Jane' given the full name 'Ms. Barbara J Jensen, III').|
|» nickName|string|false|none|The casual way to address the user in real  life, e.g., 'Bob' or 'Bobby' instead of 'Robert'.  This attribute  SHOULD NOT be used to represent a User's username (e.g., 'bjensen' or  'mpepperidge').|
|» phoneNumbers|[object]|false|none|Phone numbers for the User.  The value SHOULD be canonicalized by the service provider according to the format specified in RFC 3966, e.g., 'tel:+1-201-555-0123'. Canonical type values of 'work', 'home', 'mobile', 'fax', 'pager', and 'other'.|
|»» display|string|false|none|A human-readable phone number for display|
|»» notifications|boolean|false|none|LNA Opt-in for mobile devices (type=Mobile)|
|»» operatingSystem|string|false|none|The OS of the  device, when the phone is a cellphone type|
|»» primary|boolean|false|none|Primary device for mobile devices (type=Mobile)|
|»» type|string|false|none|A label indicating the attribute's function, e.g., 'Work', 'Home'.|
|»» value|string|false|none|Phone number value. Attempts to format to RFC3966 standards on create/update|
|» preferredLanguage|string|false|none|Indicates the User's preferred written or spoken language.  Generally used for selecting a localized user interface|
|» schemas|[string]|false|none|none|
|» timezone|string|false|none|The User's time zone in the 'Olson' time zone database format, e.g., 'America/Los_Angeles'.|
|» title|string|false|none|user's job title in the company|
|» urn:ietf:params:scim:schemas:extension:enterprise:2.0:User|object|true|none|none|
|»» companyId|string|true|none|Concur ID of the company|
|»» costCenter|string|false|none|employee cost center for product|
|»» department|string|false|none|Client supplied department name|
|»» division|string|false|none|Client supplied division name|
|»» employeeNumber|string|false|none|Client supplied employee's number within the company, unique for the company|
|»» manager|object|false|none|The manager of this user|
|»»» $ref|string|false|none|The URI of the SCIM resource representing the referenced user.|
|»»» displayName|string|false|none|The referenced user's display name|
|»»» employeeNumber|string|false|none|The referenced user's employee number, if it is an Enterprise user|
|»»» value|string|false|none|The referenced user's UUID|
|»» orgUnit|string|false|none|Client supplied org unit name|
|»» organization|string|false|none|Company name|
|»» self|object|false|none|A reference to this user|
|»»» $ref|string|false|none|The URI of the SCIM resource representing the referenced user.|
|»»» displayName|string|false|none|The referenced user's display name|
|»»» employeeNumber|string|false|none|The referenced user's employee number, if it is an Enterprise user|
|»»» value|string|false|none|The referenced user's UUID|
|»» startDate|string|false|none|Start Date, in YYYY-MM-DD format|
|»» terminationDate|string|false|none|Termination Date, in YYYY-MM-DD format, if the employee is terminated, this can also be used to calculate the data retention period|
|» userName|string|true|none|The name that can be used to login to CTE|

#### Enumerated Values

|Property|Value|
|---|---|
|type|work|
|type|home|
|type|other|
|type|billing|
|type|bank|
|type|shipping|
|type|work|
|type|home|
|type|other|
|type|other2|
|type|work2|
|type|sms|
|relationship|Spouse|
|relationship|Brother|
|relationship|Parent|
|relationship|Sister|
|relationship|Life Partner|
|relationship|Other|
|gender|Male|
|gender|Female|
|gender|Others|
|preference24Hour|h:mm AM/PM|
|preference24Hour|H:mm|
|preferenceCurrencySymbolLocation|BeforeAmount|
|preferenceCurrencySymbolLocation|AfterAmount|
|preferenceDateFormat|mm/dd/yyyy|
|preferenceDateFormat|mm.dd.yyyy|
|preferenceDateFormat|mm-dd-yyyy|
|preferenceDateFormat|dd/mm/yyyy|
|preferenceDateFormat|dd.mm.yyyy|
|preferenceDateFormat|dd-mm-yyyy|
|preferenceDateFormat|yyyy/mm/dd|
|preferenceDateFormat|yyyy.mm.dd|
|preferenceDateFormat|yyyy-mm-dd|
|preferenceDefaultCalView|day|
|preferenceDefaultCalView|week|
|preferenceDefaultCalView|month|
|preferenceDistance|mile|
|preferenceDistance|km|
|preferenceFirstDayOfWeek|Monday|
|preferenceFirstDayOfWeek|Tuesday|
|preferenceFirstDayOfWeek|Wednesday|
|preferenceFirstDayOfWeek|Thursday|
|preferenceFirstDayOfWeek|Friday|
|preferenceFirstDayOfWeek|Saturday|
|preferenceFirstDayOfWeek|Sunday|
|preferenceHourMinuteSeparator|:|
|preferenceHourMinuteSeparator|.|
|preferenceNegativeCurrencyFormat|-100|
|preferenceNegativeCurrencyFormat|(100)|
|preferenceNegativeNumberFormat|-100|
|preferenceNegativeNumberFormat|(100)|
|preferenceNumberFormat|1,000.00|
|preferenceNumberFormat|1.000,00|
|preferenceNumberFormat|1 000,00|
|preferenceNumberFormat|1'000.00|
|preferenceNumberFormat|1'000,00|
|honorificPrefix|Miss|
|honorificPrefix|Mr|
|honorificPrefix|Mrs|
|honorificPrefix|Ms|
|honorificPrefix|Mx|
|honorificPrefix|B.A.|
|honorificPrefix|B.Sc.|
|honorificPrefix|CPA|
|honorificPrefix|D.D.|
|honorificPrefix|D.D.S.|
|honorificPrefix|D.P.S.|
|honorificPrefix|Dr|
|honorificPrefix|Dr Mr|
|honorificPrefix|Dr Mrs|
|honorificPrefix|Dr Ms|
|honorificPrefix|Eng.|
|honorificPrefix|Ing.|
|honorificPrefix|Lady|
|honorificPrefix|Lord|
|honorificPrefix|M.D.|
|honorificPrefix|MBA|
|honorificPrefix|P.Eng.|
|honorificPrefix|Ph.D|
|honorificPrefix|Ph.D.|
|honorificPrefix|Prof|
|honorificPrefix|Prof Dr|
|honorificPrefix|Prof Dr Mr|
|honorificPrefix|Prof Dr Mrs|
|honorificPrefix|Prof Dr Ms|
|honorificPrefix|Prof Mr|
|honorificPrefix|Prof Mrs|
|honorificPrefix|Prof Ms|
|honorificPrefix|Rev|
|honorificPrefix|Sir|
|honorificSuffix|Jr.|
|honorificSuffix|Sr.|
|honorificSuffix|I|
|honorificSuffix|II|
|honorificSuffix|III|
|honorificSuffix|IV|
|honorificSuffix|V|
|honorificSuffix|VI|
|operatingSystem|Android Phone|
|operatingSystem|Android Tablet|
|operatingSystem|Blackberry|
|operatingSystem|iOS Phone|
|operatingSystem|iOS Tablet|
|operatingSystem|Not a smartphone|
|operatingSystem|Other iOS device|
|operatingSystem|Other smartphone|
|operatingSystem|Unknown|
|operatingSystem|Window Mobile|
|type|work|
|type|home|
|type|mobile|
|type|fax|
|type|pager|
|type|other|
|type|work2|

<aside class="success">
This operation does not require authentication
</aside>

# Schemas

<h2 id="tocS_User">User</h2>
<!-- backwards compatibility -->
<a id="schemauser"></a>
<a id="schema_User"></a>
<a id="tocSuser"></a>
<a id="tocsuser"></a>

```json
{
  "active": true,
  "addresses": [
    {
      "country": "string",
      "locality": "string",
      "postalCode": "string",
      "region": "string",
      "streetAddress": "string",
      "type": "work"
    }
  ],
  "dateOfBirth": "string",
  "displayName": "string",
  "emails": [
    {
      "dateAdded": "string",
      "dateVerified": "string",
      "notifications": true,
      "type": "work",
      "value": "string",
      "verified": true
    }
  ],
  "emergencyContacts": [
    {
      "country": "string",
      "emails": [
        "string"
      ],
      "locality": "string",
      "name": "string",
      "phones": [
        "string"
      ],
      "postalCode": "string",
      "region": "string",
      "relationship": "Spouse",
      "streetAddress": "string"
    }
  ],
  "entitlements": [
    "Expense"
  ],
  "externalId": "string",
  "gender": "Male",
  "id": "string",
  "localeOverrides": {
    "preference24Hour": "h:mm AM/PM",
    "preferenceCurrencySymbolLocation": "BeforeAmount",
    "preferenceDateFormat": "mm/dd/yyyy",
    "preferenceDefaultCalView": "day",
    "preferenceDistance": "mile",
    "preferenceEndDayViewHour": 0,
    "preferenceFirstDayOfWeek": "Monday",
    "preferenceHourMinuteSeparator": ":",
    "preferenceNegativeCurrencyFormat": "-100",
    "preferenceNegativeNumberFormat": "-100",
    "preferenceNumberFormat": "1,000.00",
    "preferenceStartDayViewHour": 0
  },
  "meta": {},
  "name": {
    "academicTitle": [
      "Dr."
    ],
    "familyName": "string",
    "familyNamePrefix": "string",
    "formatted": "string",
    "givenName": "string",
    "hasNoMiddleName": true,
    "honorificPrefix": "Miss",
    "honorificSuffix": "Jr.",
    "legalName": "string",
    "middleInitial": "string",
    "middleName": "string"
  },
  "nickName": "string",
  "phoneNumbers": [
    {
      "display": "string",
      "notifications": true,
      "operatingSystem": "Android Phone",
      "primary": true,
      "type": "work",
      "value": "string"
    }
  ],
  "preferredLanguage": "string",
  "schemas": [
    "urn:ietf:params:scim:schemas:core:2.0:User"
  ],
  "timezone": "string",
  "title": "string",
  "urn:ietf:params:scim:schemas:extension:enterprise:2.0:User": {
    "companyId": "string",
    "costCenter": "string",
    "department": "string",
    "division": "string",
    "employeeNumber": "string",
    "manager": {
      "$ref": "string",
      "displayName": "string",
      "employeeNumber": "string",
      "value": "string"
    },
    "orgUnit": "string",
    "organization": "string",
    "self": {
      "$ref": "string",
      "displayName": "string",
      "employeeNumber": "string",
      "value": "string"
    },
    "startDate": "string",
    "terminationDate": "string"
  },
  "userName": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|active|boolean|true|none|A Boolean value indicating whether the User is active.|
|addresses|[object]|false|none|A physical mailing address for this User. Canonical type values of 'work', 'home', and 'other'. This attribute is a complex type with the following sub-attributes.|
|» country|string|false|none|A two-letter country code defined in ISO 3166-1 alpha-2|
|» locality|string|false|none|The city or locality.|
|» postalCode|string|false|none|The zip code or postal code.|
|» region|string|false|none|The state or region.|
|» streetAddress|string|false|none|The full street address component, which may include house number, street name, P.O. box, and multi-line extended street address information.  This attribute MAY contain newlines.|
|» type|string|false|none|A label indicating the function of the address, e.g., 'work' or 'home'.|
|dateOfBirth|string|false|none|The user's date of birth , in YYYY-MM-DD format|
|displayName|string|false|none|The name of the User, suitable for display to end-users.|
|emails|[object]|true|none|Email addresses for the user. The value SHOULD be canonicalized by the service provider, e.g., 'bjensen@example.com' instead of 'bjensen@EXAMPLE.COM'. Canonical type values of 'work', 'home', and 'other'.|
|» dateAdded|string|false|none|The date and time the email was added to the user's profile.|
|» dateVerified|string|false|none|The date and time the email was verified|
|» notifications|boolean|false|none|Notifications opt-in for emails|
|» type|string|false|none|A label indicating the attribute's function, e.g., 'Work' or 'Home'.|
|» value|string|true|none|Email address value|
|» verified|boolean|false|none|flag to note which email has been verified by the user.|
|emergencyContacts|[object]|false|none|Emergency Contact information for the User.|
|» country|string|false|none|A two-letter country code defined in ISO 3166-1 alpha-2|
|» emails|[string]|false|none|Emails of the contact|
|» locality|string|false|none|The city or locality.|
|» name|string|true|none|Contact name.|
|» phones|[string]|false|none|Phone numbers of the contact|
|» postalCode|string|false|none|The zip code or postal code.|
|» region|string|false|none|The state or region.|
|» relationship|string|true|none|Emergency contact relationship.|
|» streetAddress|string|false|none|The full street address component, which may include house number, street name, P.O. box, and multi-line extended street address information.  This attribute MAY contain newlines.|
|entitlements|[string]|false|none|The features enabled for the user|
|externalId|string|false|none|User identifier from the provisioning client|
|gender|string|false|none|The user's gender|
|id|string|true|none|Unique identifier for the user - a uuid|
|localeOverrides|object|false|none|Support for users who want to override locale settings|
|» preference24Hour|string|false|none|preferred 24 hour format for the user|
|» preferenceCurrencySymbolLocation|string|false|none|preferred currency symbol location for the user|
|» preferenceDateFormat|string|false|none|preferred date format for the user|
|» preferenceDefaultCalView|string|false|none|preferred default calendar view for the user|
|» preferenceDistance|string|false|none|preferred distance metric|
|» preferenceEndDayViewHour|integer|false|none|preferred hour setting for the end of day, 0-23|
|» preferenceFirstDayOfWeek|string|false|none|preferred first day of the week for the user|
|» preferenceHourMinuteSeparator|string|false|none|preferred separator between hour and minute|
|» preferenceNegativeCurrencyFormat|string|false|none|preferred negative currency format for the user|
|» preferenceNegativeNumberFormat|string|false|none|preferred negative number format for the user|
|» preferenceNumberFormat|string|false|none|preferred number format for the user|
|» preferenceStartDayViewHour|integer|false|none|preferred start of day for the user, from 1|
|meta|object|false|none|none|
|name|object|true|none|The user's name|
|» academicTitle|[string]|false|none|Title signifying level of academic achievement|
|» familyName|string|true|none|The family name of the User, or last name in most Western languages (e.g., 'Jensen' given the full name 'Ms. Barbara J Jensen, III').|
|» familyNamePrefix|string|false|none|The family name prefix of the User (e.g. 'van' given the full name 'Vincent van Gogh')|
|» formatted|string|false|none|The full name, formatted for display (e.g., 'Jensen, Barbara Jane').|
|» givenName|string|true|none|The given name of the User, or first name in most Western languages (e.g., 'Barbara' given the full name 'Ms. Barbara J Jensen, III').|
|» hasNoMiddleName|boolean|false|none|A boolean indicating that the user does not have a middle name|
|» honorificPrefix|string|false|none|The honorific prefix(es) of the User, or title in most Western languages (e.g., 'Ms.' given the full name 'Ms. Barbara J Jensen, III').|
|» honorificSuffix|string|false|none|The honorific suffix(es) of the User, or  suffix in most Western languages (e.g., 'III' given the full name  'Ms. Barbara J Jensen, III').|
|» legalName|string|false|none|The legal name of the User (e.g., 'Jane' given the full name 'Ms. Barbara J Jensen, III').|
|» middleInitial|string|false|none|middle initial, if the user has a middle name|
|» middleName|string|false|none|The middle name(s) of the User (e.g., 'Jane' given the full name 'Ms. Barbara J Jensen, III').|
|nickName|string|false|none|The casual way to address the user in real  life, e.g., 'Bob' or 'Bobby' instead of 'Robert'.  This attribute  SHOULD NOT be used to represent a User's username (e.g., 'bjensen' or  'mpepperidge').|
|phoneNumbers|[object]|false|none|Phone numbers for the User.  The value SHOULD be canonicalized by the service provider according to the format specified in RFC 3966, e.g., 'tel:+1-201-555-0123'. Canonical type values of 'work', 'home', 'mobile', 'fax', 'pager', and 'other'.|
|» display|string|false|none|A human-readable phone number for display|
|» notifications|boolean|false|none|LNA Opt-in for mobile devices (type=Mobile)|
|» operatingSystem|string|false|none|The OS of the  device, when the phone is a cellphone type|
|» primary|boolean|false|none|Primary device for mobile devices (type=Mobile)|
|» type|string|false|none|A label indicating the attribute's function, e.g., 'Work', 'Home'.|
|» value|string|false|none|Phone number value. Attempts to format to RFC3966 standards on create/update|
|preferredLanguage|string|false|none|Indicates the User's preferred written or spoken language.  Generally used for selecting a localized user interface|
|schemas|[string]|false|none|none|
|timezone|string|false|none|The User's time zone in the 'Olson' time zone database format, e.g., 'America/Los_Angeles'.|
|title|string|false|none|user's job title in the company|
|urn:ietf:params:scim:schemas:extension:enterprise:2.0:User|object|true|none|none|
|» companyId|string|true|none|Concur ID of the company|
|» costCenter|string|false|none|employee cost center for product|
|» department|string|false|none|Client supplied department name|
|» division|string|false|none|Client supplied division name|
|» employeeNumber|string|false|none|Client supplied employee's number within the company, unique for the company|
|» manager|object|false|none|The manager of this user|
|»» $ref|string|false|none|The URI of the SCIM resource representing the referenced user.|
|»» displayName|string|false|none|The referenced user's display name|
|»» employeeNumber|string|false|none|The referenced user's employee number, if it is an Enterprise user|
|»» value|string|false|none|The referenced user's UUID|
|» orgUnit|string|false|none|Client supplied org unit name|
|» organization|string|false|none|Company name|
|» self|object|false|none|A reference to this user|
|»» $ref|string|false|none|The URI of the SCIM resource representing the referenced user.|
|»» displayName|string|false|none|The referenced user's display name|
|»» employeeNumber|string|false|none|The referenced user's employee number, if it is an Enterprise user|
|»» value|string|false|none|The referenced user's UUID|
|» startDate|string|false|none|Start Date, in YYYY-MM-DD format|
|» terminationDate|string|false|none|Termination Date, in YYYY-MM-DD format, if the employee is terminated, this can also be used to calculate the data retention period|
|userName|string|true|none|The name that can be used to login to CTE|

#### Enumerated Values

|Property|Value|
|---|---|
|type|work|
|type|home|
|type|other|
|type|billing|
|type|bank|
|type|shipping|
|type|work|
|type|home|
|type|other|
|type|other2|
|type|work2|
|type|sms|
|relationship|Spouse|
|relationship|Brother|
|relationship|Parent|
|relationship|Sister|
|relationship|Life Partner|
|relationship|Other|
|gender|Male|
|gender|Female|
|gender|Others|
|preference24Hour|h:mm AM/PM|
|preference24Hour|H:mm|
|preferenceCurrencySymbolLocation|BeforeAmount|
|preferenceCurrencySymbolLocation|AfterAmount|
|preferenceDateFormat|mm/dd/yyyy|
|preferenceDateFormat|mm.dd.yyyy|
|preferenceDateFormat|mm-dd-yyyy|
|preferenceDateFormat|dd/mm/yyyy|
|preferenceDateFormat|dd.mm.yyyy|
|preferenceDateFormat|dd-mm-yyyy|
|preferenceDateFormat|yyyy/mm/dd|
|preferenceDateFormat|yyyy.mm.dd|
|preferenceDateFormat|yyyy-mm-dd|
|preferenceDefaultCalView|day|
|preferenceDefaultCalView|week|
|preferenceDefaultCalView|month|
|preferenceDistance|mile|
|preferenceDistance|km|
|preferenceFirstDayOfWeek|Monday|
|preferenceFirstDayOfWeek|Tuesday|
|preferenceFirstDayOfWeek|Wednesday|
|preferenceFirstDayOfWeek|Thursday|
|preferenceFirstDayOfWeek|Friday|
|preferenceFirstDayOfWeek|Saturday|
|preferenceFirstDayOfWeek|Sunday|
|preferenceHourMinuteSeparator|:|
|preferenceHourMinuteSeparator|.|
|preferenceNegativeCurrencyFormat|-100|
|preferenceNegativeCurrencyFormat|(100)|
|preferenceNegativeNumberFormat|-100|
|preferenceNegativeNumberFormat|(100)|
|preferenceNumberFormat|1,000.00|
|preferenceNumberFormat|1.000,00|
|preferenceNumberFormat|1 000,00|
|preferenceNumberFormat|1'000.00|
|preferenceNumberFormat|1'000,00|
|honorificPrefix|Miss|
|honorificPrefix|Mr|
|honorificPrefix|Mrs|
|honorificPrefix|Ms|
|honorificPrefix|Mx|
|honorificPrefix|B.A.|
|honorificPrefix|B.Sc.|
|honorificPrefix|CPA|
|honorificPrefix|D.D.|
|honorificPrefix|D.D.S.|
|honorificPrefix|D.P.S.|
|honorificPrefix|Dr|
|honorificPrefix|Dr Mr|
|honorificPrefix|Dr Mrs|
|honorificPrefix|Dr Ms|
|honorificPrefix|Eng.|
|honorificPrefix|Ing.|
|honorificPrefix|Lady|
|honorificPrefix|Lord|
|honorificPrefix|M.D.|
|honorificPrefix|MBA|
|honorificPrefix|P.Eng.|
|honorificPrefix|Ph.D|
|honorificPrefix|Ph.D.|
|honorificPrefix|Prof|
|honorificPrefix|Prof Dr|
|honorificPrefix|Prof Dr Mr|
|honorificPrefix|Prof Dr Mrs|
|honorificPrefix|Prof Dr Ms|
|honorificPrefix|Prof Mr|
|honorificPrefix|Prof Mrs|
|honorificPrefix|Prof Ms|
|honorificPrefix|Rev|
|honorificPrefix|Sir|
|honorificSuffix|Jr.|
|honorificSuffix|Sr.|
|honorificSuffix|I|
|honorificSuffix|II|
|honorificSuffix|III|
|honorificSuffix|IV|
|honorificSuffix|V|
|honorificSuffix|VI|
|operatingSystem|Android Phone|
|operatingSystem|Android Tablet|
|operatingSystem|Blackberry|
|operatingSystem|iOS Phone|
|operatingSystem|iOS Tablet|
|operatingSystem|Not a smartphone|
|operatingSystem|Other iOS device|
|operatingSystem|Other smartphone|
|operatingSystem|Unknown|
|operatingSystem|Window Mobile|
|type|work|
|type|home|
|type|mobile|
|type|fax|
|type|pager|
|type|other|
|type|work2|

<h2 id="tocS_UserList">UserList</h2>
<!-- backwards compatibility -->
<a id="schemauserlist"></a>
<a id="schema_UserList"></a>
<a id="tocSuserlist"></a>
<a id="tocsuserlist"></a>

```json
{
  "totalResults": 0,
  "itemsPerPage": 0,
  "startIndex": 0,
  "schemas": [
    "urn:ietf:params:scim:api:messages:2.0:ListResponse"
  ],
  "Resources": [
    {
      "active": true,
      "addresses": [
        {
          "country": "string",
          "locality": "string",
          "postalCode": "string",
          "region": "string",
          "streetAddress": "string",
          "type": "work"
        }
      ],
      "dateOfBirth": "string",
      "displayName": "string",
      "emails": [
        {
          "dateAdded": "string",
          "dateVerified": "string",
          "notifications": true,
          "type": "work",
          "value": "string",
          "verified": true
        }
      ],
      "emergencyContacts": [
        {
          "country": "string",
          "emails": [
            "string"
          ],
          "locality": "string",
          "name": "string",
          "phones": [
            "string"
          ],
          "postalCode": "string",
          "region": "string",
          "relationship": "Spouse",
          "streetAddress": "string"
        }
      ],
      "entitlements": [
        "Expense"
      ],
      "externalId": "string",
      "gender": "Male",
      "id": "string",
      "localeOverrides": {
        "preference24Hour": "h:mm AM/PM",
        "preferenceCurrencySymbolLocation": "BeforeAmount",
        "preferenceDateFormat": "mm/dd/yyyy",
        "preferenceDefaultCalView": "day",
        "preferenceDistance": "mile",
        "preferenceEndDayViewHour": 0,
        "preferenceFirstDayOfWeek": "Monday",
        "preferenceHourMinuteSeparator": ":",
        "preferenceNegativeCurrencyFormat": "-100",
        "preferenceNegativeNumberFormat": "-100",
        "preferenceNumberFormat": "1,000.00",
        "preferenceStartDayViewHour": 0
      },
      "meta": {},
      "name": {
        "academicTitle": [
          "Dr."
        ],
        "familyName": "string",
        "familyNamePrefix": "string",
        "formatted": "string",
        "givenName": "string",
        "hasNoMiddleName": true,
        "honorificPrefix": "Miss",
        "honorificSuffix": "Jr.",
        "legalName": "string",
        "middleInitial": "string",
        "middleName": "string"
      },
      "nickName": "string",
      "phoneNumbers": [
        {
          "display": "string",
          "notifications": true,
          "operatingSystem": "Android Phone",
          "primary": true,
          "type": "work",
          "value": "string"
        }
      ],
      "preferredLanguage": "string",
      "schemas": [
        "urn:ietf:params:scim:schemas:core:2.0:User"
      ],
      "timezone": "string",
      "title": "string",
      "urn:ietf:params:scim:schemas:extension:enterprise:2.0:User": {
        "companyId": "string",
        "costCenter": "string",
        "department": "string",
        "division": "string",
        "employeeNumber": "string",
        "manager": {
          "$ref": "string",
          "displayName": "string",
          "employeeNumber": "string",
          "value": "string"
        },
        "orgUnit": "string",
        "organization": "string",
        "self": {
          "$ref": "string",
          "displayName": "string",
          "employeeNumber": "string",
          "value": "string"
        },
        "startDate": "string",
        "terminationDate": "string"
      },
      "userName": "string"
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|totalResults|integer|false|none|The total number of results matching the client query|
|itemsPerPage|integer|false|none|The number of query results returned in a query response page|
|startIndex|integer|false|none|The 1-based index of the first result in the current set of query results|
|schemas|[string]|false|none|none|
|Resources|[[User](#schemauser)]|false|none|none|

<h2 id="tocS_Company">Company</h2>
<!-- backwards compatibility -->
<a id="schemacompany"></a>
<a id="schema_Company"></a>
<a id="tocScompany"></a>
<a id="tocscompany"></a>

```json
{
  "active": true,
  "addresses": [
    {
      "country": "string",
      "locality": "string",
      "postalCode": "string",
      "region": "string",
      "streetAddress": "string"
    }
  ],
  "companyDomain": "string",
  "contact": {
    "country": "string",
    "emails": [
      "string"
    ],
    "locality": "string",
    "name": "string",
    "phones": [
      "string"
    ],
    "postalCode": "string",
    "region": "string",
    "streetAddress": "string"
  },
  "defaultLanguage": "string",
  "entitlements": [
    "Expense"
  ],
  "id": "string",
  "internetDomain": "string",
  "meta": {},
  "name": "string",
  "schemas": [
    "string"
  ],
  "urn:ietf:params:scim:schemas:extension:authentication:2.0:Company": {
    "loginPolicy": {
      "hideForgotLoginIdLink": true,
      "loginFailureLockoutDuration": 0,
      "loginFailureWindowDuration": 0,
      "loginFailuresAllowed": 0,
      "loginIPRestriction": "string",
      "loginOneTimeLinkExpirationLength": 0,
      "loginViaSsoOnly": true
    },
    "passwordPolicy": {
      "daysUntilExpiration": 0,
      "expirePasswordOnUserCreation": true,
      "maxLength": 0,
      "minLength": 0,
      "mobileAuthenticationLifetime": 0,
      "mobileMinLength": 0,
      "mobileRequiresMixedCase": true,
      "mobileRequiresNonalphanum": true,
      "numGenerationsBeforeCanReuse": 0,
      "numSecurityQuestions": 0,
      "numSecurityQuestionsUsersPick": 0,
      "passwordResetEmailPolicy": "never",
      "passwordResetSupportEmail": "string",
      "requiresMixedCase": true,
      "requiresNonAlpha": true,
      "requiresNonAlphanum": true,
      "requiresNumber": true,
      "requiresSecurityQuestions": true,
      "restrictPasswordResetOncePerDay": true
    }
  },
  "urn:ietf:params:scim:schemas:extension:notification:2.0:Company": {
    "channels": [
      "Slack"
    ],
    "enabled": true
  },
  "urn:ietf:params:scim:schemas:extension:sap:2.0:Company": {
    "tenantIdSpend": "string",
    "tenantIdTravel": "string"
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|active|boolean|true|none|A Boolean value indicating whether the company is active.|
|addresses|[object]|false|none|none|
|» country|string|false|none|A two-letter country code defined in ISO 3166-1 alpha-2|
|» locality|string|false|none|The city or locality.|
|» postalCode|string|false|none|The zip code or postal code.|
|» region|string|false|none|The state or region.|
|» streetAddress|string|false|none|The full street address component, which may include house number, street name, P.O. box, and multi-line extended street address information.  This attribute MAY contain newlines.|
|companyDomain|string|false|none|The company's company domain name|
|contact|object|false|none|none|
|» country|string|false|none|A two-letter country code defined in ISO 3166-1 alpha-2|
|» emails|[string]|false|none|Emails of the contact|
|» locality|string|false|none|The city or locality.|
|» name|string|true|none|Contact name.|
|» phones|[string]|false|none|Phone numbers of the contact|
|» postalCode|string|false|none|The zip code or postal code.|
|» region|string|false|none|The state or region.|
|» streetAddress|string|false|none|The full street address component, which may include house number, street name, P.O. box, and multi-line extended street address information.  This attribute MAY contain newlines.|
|defaultLanguage|string|false|none|Indicates the default language for the company.|
|entitlements|[string]|false|none|The features enabled for the company|
|id|string|true|none|Unique identifier for the company - a uuid|
|internetDomain|string|false|none|The company's internet domain name|
|meta|object|false|none|none|
|name|string|false|none|The name of the company|
|schemas|[string]|false|none|none|
|urn:ietf:params:scim:schemas:extension:authentication:2.0:Company|object|false|none|none|
|» loginPolicy|object|false|none|none|
|»» hideForgotLoginIdLink|boolean|false|none|Hide Forgot LoginId Link|
|»» loginFailureLockoutDuration|integer|false|none|Login Failure Lockout Duration|
|»» loginFailureWindowDuration|integer|false|none|Login Failure Window Duration|
|»» loginFailuresAllowed|integer|false|none|Login Failures Allowed|
|»» loginIPRestriction|string|false|none|login IP Restriction|
|»» loginOneTimeLinkExpirationLength|integer|false|none|Login One Time Link Expiration Length|
|»» loginViaSsoOnly|boolean|false|none|login Via SSO Only|
|» passwordPolicy|object|false|none|none|
|»» daysUntilExpiration|integer|false|none|Number of days Until expiration|
|»» expirePasswordOnUserCreation|boolean|false|none|Expire Password On User Creation|
|»» maxLength|integer|false|none|Maximum length|
|»» minLength|integer|false|none|Minimum length|
|»» mobileAuthenticationLifetime|integer|false|none|Mobile session timeout in seconds|
|»» mobileMinLength|integer|false|none|Min Length for Mobile|
|»» mobileRequiresMixedCase|boolean|false|none|Require mixed cases for Mobile|
|»» mobileRequiresNonalphanum|boolean|false|none|Require None alpha numberic for Mobile|
|»» numGenerationsBeforeCanReuse|integer|false|none|Number of Generations Before the password can be reused|
|»» numSecurityQuestions|integer|false|none|Number of security questions|
|»» numSecurityQuestionsUsersPick|integer|false|none|Number of security questions users can pick|
|»» passwordResetEmailPolicy|string|false|none|When should password reset password email shall be sent|
|»» passwordResetSupportEmail|string|false|none|The FROM address of the password or PIN reset email|
|»» requiresMixedCase|boolean|false|none|Require mixed cases|
|»» requiresNonAlpha|boolean|false|none|Requires NonAlpha|
|»» requiresNonAlphanum|boolean|false|none|Requires NonAlphaNum|
|»» requiresNumber|boolean|false|none|Require numbers|
|»» requiresSecurityQuestions|boolean|false|none|Require security questions|
|»» restrictPasswordResetOncePerDay|boolean|false|none|restrict Password Reset Once Per Day|
|urn:ietf:params:scim:schemas:extension:notification:2.0:Company|object|false|none|none|
|» channels|[string]|false|none|none|
|» enabled|boolean|false|none|none|
|urn:ietf:params:scim:schemas:extension:sap:2.0:Company|object|false|none|none|
|» tenantIdSpend|string|false|none|Spend tenant ID for the company|
|» tenantIdTravel|string|false|none|Travel tenant ID for the company|

#### Enumerated Values

|Property|Value|
|---|---|
|passwordResetEmailPolicy|never|
|passwordResetEmailPolicy|anyTime|
|passwordResetEmailPolicy|afterFirstLogin|

<h2 id="tocS_ConcurError">ConcurError</h2>
<!-- backwards compatibility -->
<a id="schemaconcurerror"></a>
<a id="schema_ConcurError"></a>
<a id="tocSconcurerror"></a>
<a id="tocsconcurerror"></a>

```json
{
  "messages": [
    {
      "code": "string",
      "message": "string",
      "schemaPath": "string",
      "type": "error"
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|messages|[object]|false|none|Additional messages in case of errors / warnings|
|» code|string|true|none|Message Code|
|» message|string|false|none|Message description|
|» schemaPath|string|false|none|Relative schema path of attribute|
|» type|string|true|none|Message Type|

#### Enumerated Values

|Property|Value|
|---|---|
|type|error|
|type|warning|

<h2 id="tocS_ErrorResponse">ErrorResponse</h2>
<!-- backwards compatibility -->
<a id="schemaerrorresponse"></a>
<a id="schema_ErrorResponse"></a>
<a id="tocSerrorresponse"></a>
<a id="tocserrorresponse"></a>

```json
{
  "scimType": "string",
  "detail": "string",
  "status": "string",
  "urn:ietf:params:scim:api:messages:concur:2.0:Error": {
    "messages": [
      {
        "code": "string",
        "message": "string",
        "schemaPath": "string",
        "type": "error"
      }
    ]
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|scimType|string|false|none|SCIM detail error keyword|
|detail|string|false|none|Human readable message|
|status|string|true|none|HTTP status code|
|urn:ietf:params:scim:api:messages:concur:2.0:Error|[ConcurError](#schemaconcurerror)|false|none|none|

<h2 id="tocS_SchemaExtension">SchemaExtension</h2>
<!-- backwards compatibility -->
<a id="schemaschemaextension"></a>
<a id="schema_SchemaExtension"></a>
<a id="tocSschemaextension"></a>
<a id="tocsschemaextension"></a>

```json
{
  "schema": "string",
  "required": true
}

```

Describes an extension of a schema

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|schema|string|true|none|The string identifier of the extension|
|required|boolean|true|none|Whether this existention is a required part of the schema|

<h2 id="tocS_ResourceType">ResourceType</h2>
<!-- backwards compatibility -->
<a id="schemaresourcetype"></a>
<a id="schema_ResourceType"></a>
<a id="tocSresourcetype"></a>
<a id="tocsresourcetype"></a>

```json
{
  "attributes": [
    {
      "schema": "string",
      "required": true
    }
  ],
  "description": "string",
  "endpoint": "string",
  "id": "string",
  "name": "string",
  "schema": "string"
}

```

Describes the extension and metadata constituting a resource like a user.

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|attributes|[[SchemaExtension](#schemaschemaextension)]|true|none|The resource's extensions|
|description|string|true|none|The resource's description|
|endpoint|string|true|none|The resource's HTTP addressable endpoint relative to the base URL, e.g. /Users.|
|id|string|true|none|The resource's id, e.g. urn:scim:schemas:core:1.0:User|
|name|string|true|none|The resource's name, e.g. "User"|
|schema|string|true|none|The resource's associated schema, e.g. urn:scim:schemas:core:1.0|

<h2 id="tocS_AuthenticationSchemes">AuthenticationSchemes</h2>
<!-- backwards compatibility -->
<a id="schemaauthenticationschemes"></a>
<a id="schema_AuthenticationSchemes"></a>
<a id="tocSauthenticationschemes"></a>
<a id="tocsauthenticationschemes"></a>

```json
{
  "description": "string",
  "documentationUrl": "string",
  "name": "string",
  "specUrl": "string"
}

```

Specifies supported Authentication Scheme properties

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|description|string|true|none|The description of the Authentication Scheme|
|documentationUrl|string|true|none|A HTTP addressable URL pointing to the Authentication Scheme's usage documentation|
|name|string|true|none|The common authentication scheme name, e.g. HTTP Basic|
|specUrl|string|true|none|A HTTP addressable URL pointing to the Authentication Scheme's specification|

<h2 id="tocS_ServiceProviderConfigSetting">ServiceProviderConfigSetting</h2>
<!-- backwards compatibility -->
<a id="schemaserviceproviderconfigsetting"></a>
<a id="schema_ServiceProviderConfigSetting"></a>
<a id="tocSserviceproviderconfigsetting"></a>
<a id="tocsserviceproviderconfigsetting"></a>

```json
{
  "supported": true
}

```

Details about feature support for this service provider

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|supported|boolean|false|none|Whether the feature is supported|

<h2 id="tocS_ServiceProviderConfig">ServiceProviderConfig</h2>
<!-- backwards compatibility -->
<a id="schemaserviceproviderconfig"></a>
<a id="schema_ServiceProviderConfig"></a>
<a id="tocSserviceproviderconfig"></a>
<a id="tocsserviceproviderconfig"></a>

```json
{
  "authenticationSchemes": {
    "description": "string",
    "documentationUrl": "string",
    "name": "string",
    "specUrl": "string"
  },
  "bulk": {
    "supported": true
  },
  "changePassword": {
    "supported": true
  },
  "documentationUrl": "string",
  "etag": {
    "supported": true
  },
  "filter": {
    "supported": true
  },
  "patch": {
    "supported": true
  },
  "sort": {
    "supported": true
  }
}

```

Represents the Service Provider's configuration

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|authenticationSchemes|[AuthenticationSchemes](#schemaauthenticationschemes)|true|none|Specifies supported Authentication Scheme properties|
|bulk|[ServiceProviderConfigSetting](#schemaserviceproviderconfigsetting)|true|none|Details about feature support for this service provider|
|changePassword|[ServiceProviderConfigSetting](#schemaserviceproviderconfigsetting)|true|none|Details about feature support for this service provider|
|documentationUrl|string|true|none|An HTTP addressable URL pointing to the Service Provider's help documentation|
|etag|[ServiceProviderConfigSetting](#schemaserviceproviderconfigsetting)|true|none|Details about feature support for this service provider|
|filter|[ServiceProviderConfigSetting](#schemaserviceproviderconfigsetting)|true|none|Details about feature support for this service provider|
|patch|[ServiceProviderConfigSetting](#schemaserviceproviderconfigsetting)|true|none|Details about feature support for this service provider|
|sort|[ServiceProviderConfigSetting](#schemaserviceproviderconfigsetting)|true|none|Details about feature support for this service provider|

