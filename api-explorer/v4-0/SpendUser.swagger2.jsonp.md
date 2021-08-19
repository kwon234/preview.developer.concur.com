<!-- Generator: Widdershins v4.0.1 -->

<h1 id="spend-user-service">Spend User Service vcandidate</h1>

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

Rest API for Spend User Service

Base URLs:

* <a href="https://sus.k8s.cnqr.tech">https://sus.k8s.cnqr.tech</a>

<a href="http://www.concur.com">Terms of service</a>
Email: <a href="mailto:Team_Up@sap.com">Team Up</a> 
License: <a href="http://www.concur.com">SAP Concur</a>

<h1 id="spend-user-service-spend-user-apis">Spend User APIs</h1>

## getUser

<a id="opIdgetUser"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://sus.k8s.cnqr.tech/spend/v4/Users/{uuid} \
  -H 'Accept: application/json'

```

```http
GET https://sus.k8s.cnqr.tech/spend/v4/Users/{uuid} HTTP/1.1
Host: sus.k8s.cnqr.tech
Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('https://sus.k8s.cnqr.tech/spend/v4/Users/{uuid}',
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

result = RestClient.get 'https://sus.k8s.cnqr.tech/spend/v4/Users/{uuid}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://sus.k8s.cnqr.tech/spend/v4/Users/{uuid}', headers = headers)

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
    $response = $client->request('GET','https://sus.k8s.cnqr.tech/spend/v4/Users/{uuid}', array(
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
URL obj = new URL("https://sus.k8s.cnqr.tech/spend/v4/Users/{uuid}");
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
    req, err := http.NewRequest("GET", "https://sus.k8s.cnqr.tech/spend/v4/Users/{uuid}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /spend/v4/Users/{uuid}`

Get the aggregated user.

<h3 id="getuser-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|uuid|path|string(uuid)|true|UUID|

> Example responses

> 200 Response

```json
{
  "schemas": [
    "string"
  ],
  "externalId": "string",
  "meta": {
    "resourceType": "string",
    "created": "2019-08-24T14:15:22Z",
    "lastModified": "2019-08-24T14:15:22Z",
    "location": "http://example.com",
    "version": "string"
  },
  "urn:ietf:params:scim:schemas:extension:spend:2.0:User": {
    "reimbursementCurrency": "USD",
    "reimbursementType": "ADP_PAYROLL",
    "ledgerCode": "DEFAULT",
    "country": "US",
    "budgetCountryCode": "US",
    "stateProvince": "WA",
    "locale": "en-US",
    "cashAdvanceAccountCode": "string",
    "testEmployee": true,
    "nonEmployee": true,
    "biManager": {
      "value": "a860a344-d7b2-406e-828e-8d442f23f344",
      "displayName": "string",
      "employeeNumber": "string",
      "$ref": "http://example.com"
    },
    "customData": [
      {
        "id": "custom1",
        "value": "string"
      }
    ]
  },
  "urn:ietf:params:scim:schemas:extension:spend:2.0:Approver": {
    "report": [
      {
        "approver": {
          "value": "a860a344-d7b2-406e-828e-8d442f23f344",
          "displayName": "string",
          "employeeNumber": "string",
          "$ref": "http://example.com"
        },
        "primary": true
      }
    ],
    "cashAdvance": [
      {
        "approver": {
          "value": "a860a344-d7b2-406e-828e-8d442f23f344",
          "displayName": "string",
          "employeeNumber": "string",
          "$ref": "http://example.com"
        },
        "primary": true
      }
    ],
    "request": [
      {
        "approver": {
          "value": "a860a344-d7b2-406e-828e-8d442f23f344",
          "displayName": "string",
          "employeeNumber": "string",
          "$ref": "http://example.com"
        },
        "primary": true
      }
    ],
    "invoice": [
      {
        "approver": {
          "value": "a860a344-d7b2-406e-828e-8d442f23f344",
          "displayName": "string",
          "employeeNumber": "string",
          "$ref": "http://example.com"
        },
        "primary": true
      }
    ],
    "purchaseRequest": [
      {
        "approver": {
          "value": "a860a344-d7b2-406e-828e-8d442f23f344",
          "displayName": "string",
          "employeeNumber": "string",
          "$ref": "http://example.com"
        },
        "primary": true
      }
    ],
    "statement": [
      {
        "approver": {
          "value": "a860a344-d7b2-406e-828e-8d442f23f344",
          "displayName": "string",
          "employeeNumber": "string",
          "$ref": "http://example.com"
        },
        "primary": true
      }
    ],
    "budget": [
      {
        "approver": {
          "value": "a860a344-d7b2-406e-828e-8d442f23f344",
          "displayName": "string",
          "employeeNumber": "string",
          "$ref": "http://example.com"
        },
        "primary": true
      }
    ]
  },
  "urn:ietf:params:scim:schemas:extension:spend:2.0:Delegate": {
    "expense": [
      {
        "canApprove": true,
        "canPrepare": true,
        "canPrepareForApproval": true,
        "canReceiveApprovalEmail": true,
        "canReceiveEmail": true,
        "canSubmit": true,
        "canSubmitTravelRequest": true,
        "canUseBi": true,
        "canViewReceipt": true,
        "delegate": {
          "value": "a860a344-d7b2-406e-828e-8d442f23f344",
          "displayName": "string",
          "employeeNumber": "string",
          "$ref": "http://example.com"
        },
        "temporaryDelegation": {
          "temporaryDelegationFromDate": "2020-09-20T22:35:36.532Z",
          "temporaryDelegationToDate": "2020-12-20T22:35:36.532Z"
        }
      }
    ],
    "payment": [
      {
        "canApprove": true,
        "canPrepare": true,
        "canPrepareForApproval": true,
        "canReceiveApprovalEmail": true,
        "canReceiveEmail": true,
        "canSubmit": true,
        "canSubmitTravelRequest": true,
        "canUseBi": true,
        "canViewReceipt": true,
        "delegate": {
          "value": "a860a344-d7b2-406e-828e-8d442f23f344",
          "displayName": "string",
          "employeeNumber": "string",
          "$ref": "http://example.com"
        },
        "temporaryDelegation": {
          "temporaryDelegationFromDate": "2020-09-20T22:35:36.532Z",
          "temporaryDelegationToDate": "2020-12-20T22:35:36.532Z"
        }
      }
    ],
    "purchaseRequest": [
      {
        "canApprove": true,
        "canPrepare": true,
        "canPrepareForApproval": true,
        "canReceiveApprovalEmail": true,
        "canReceiveEmail": true,
        "canSubmit": true,
        "canSubmitTravelRequest": true,
        "canUseBi": true,
        "canViewReceipt": true,
        "delegate": {
          "value": "a860a344-d7b2-406e-828e-8d442f23f344",
          "displayName": "string",
          "employeeNumber": "string",
          "$ref": "http://example.com"
        },
        "temporaryDelegation": {
          "temporaryDelegationFromDate": "2020-09-20T22:35:36.532Z",
          "temporaryDelegationToDate": "2020-12-20T22:35:36.532Z"
        }
      }
    ]
  },
  "urn:ietf:params:scim:schemas:extension:spend:2.0:Role": {
    "roles": [
      {
        "roleName": "EXP_FB_TAX_ADMIN",
        "roleGroups": [
          "string"
        ]
      }
    ]
  },
  "urn:ietf:params:scim:schemas:extension:spend:2.0:UserPreference": {
    "showImagingIntro": true,
    "expenseAuditRequired": "REQUIRED",
    "allowCreditCardTransArrivalEmails": true,
    "allowReceiptImageAvailEmails": true,
    "promptForCardTransactionsOnReport": true,
    "autoAddTripCardTransOnReport": true,
    "promptForReportPrintFormat": false,
    "defaultReportPrintFormat": "DETAILED",
    "showTotalOnReport": true,
    "showExpenseOnReport": "ALL",
    "showInstructHelpPanel": true,
    "useQuickItinAsDefault": true,
    "allowAutoCreateTripReport": true
  },
  "urn:ietf:params:scim:schemas:extension:enterprise:2.0:Payroll": {
    "adp": {
      "companyCode": "string",
      "deductionCode": "string",
      "employeeFileNumber": "string"
    }
  },
  "urn:ietf:params:scim:schemas:extension:spend:2.0:WorkflowPreference": {
    "emailStatusChangeOnCashAdvance": true,
    "emailAwaitApprovalOnCashAdvance": true,
    "emailStatusChangeOnReport": true,
    "emailAwaitApprovalOnReport": true,
    "promptForApproverOnReportSubmit": true,
    "emailStatusChangeOnTravelRequest": true,
    "emailAwaitApprovalOnTravelRequest": true,
    "promptForApproverOnTravelRequestSubmit": true,
    "emailStatusChangeOnPayment": true,
    "emailAwaitApprovalOnPayment": true,
    "promptForApproverOnPaymentSubmit": true
  }
}
```

<h3 id="getuser-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[FullSpendUser](#schemafullspenduser)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Invalid Request|[ErrorMessageResponse](#schemaerrormessageresponse)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|UnAuthorized|[ErrorMessageResponse](#schemaerrormessageresponse)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[ErrorMessageResponse](#schemaerrormessageresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|User Not Found|[ErrorMessageResponse](#schemaerrormessageresponse)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Error|[ErrorMessageResponse](#schemaerrormessageresponse)|

<aside class="success">
This operation does not require authentication
</aside>

## getSpendUsers

<a id="opIdgetSpendUsers"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://sus.k8s.cnqr.tech/spend/v4/Users?searchRequest=startIndex,1,itemsPerPage,100,filter,urn%3Aietf%3Aparams%3Ascim%3Aschemas%3Aextension%3Aspend%3A2.0%3AUser%3Acountry%20eq%20%22US%22 \
  -H 'Accept: application/json'

```

```http
GET https://sus.k8s.cnqr.tech/spend/v4/Users?searchRequest=startIndex,1,itemsPerPage,100,filter,urn%3Aietf%3Aparams%3Ascim%3Aschemas%3Aextension%3Aspend%3A2.0%3AUser%3Acountry%20eq%20%22US%22 HTTP/1.1
Host: sus.k8s.cnqr.tech
Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('https://sus.k8s.cnqr.tech/spend/v4/Users?searchRequest=startIndex,1,itemsPerPage,100,filter,urn%3Aietf%3Aparams%3Ascim%3Aschemas%3Aextension%3Aspend%3A2.0%3AUser%3Acountry%20eq%20%22US%22',
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

result = RestClient.get 'https://sus.k8s.cnqr.tech/spend/v4/Users',
  params: {
  'searchRequest' => '[SearchRequest](#schemasearchrequest)'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://sus.k8s.cnqr.tech/spend/v4/Users', params={
  'searchRequest': {
  "startIndex": 1,
  "itemsPerPage": 100,
  "filter": "urn:ietf:params:scim:schemas:extension:spend:2.0:User:country eq \"US\""
}
}, headers = headers)

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
    $response = $client->request('GET','https://sus.k8s.cnqr.tech/spend/v4/Users', array(
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
URL obj = new URL("https://sus.k8s.cnqr.tech/spend/v4/Users?searchRequest=startIndex,1,itemsPerPage,100,filter,urn%3Aietf%3Aparams%3Ascim%3Aschemas%3Aextension%3Aspend%3A2.0%3AUser%3Acountry%20eq%20%22US%22");
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
    req, err := http.NewRequest("GET", "https://sus.k8s.cnqr.tech/spend/v4/Users", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /spend/v4/Users`

Get the filtered and paginated spend users from the specified company

<h3 id="getspendusers-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|searchRequest|query|[SearchRequest](#schemasearchrequest)|true|none|

> Example responses

> 200 Response

```json
{
  "id": "string",
  "externalId": "string",
  "meta": {
    "resourceType": "string",
    "created": "2019-08-24T14:15:22Z",
    "lastModified": "2019-08-24T14:15:22Z",
    "location": "http://example.com",
    "version": "string"
  },
  "totalResults": 0,
  "Resources": [
    {
      "schemas": [
        "string"
      ],
      "externalId": "string",
      "meta": {
        "resourceType": "string",
        "created": "2019-08-24T14:15:22Z",
        "lastModified": "2019-08-24T14:15:22Z",
        "location": "http://example.com",
        "version": "string"
      },
      "urn:ietf:params:scim:schemas:extension:spend:2.0:User": {
        "reimbursementCurrency": "USD",
        "reimbursementType": "ADP_PAYROLL",
        "ledgerCode": "DEFAULT",
        "country": "US",
        "budgetCountryCode": "US",
        "stateProvince": "WA",
        "locale": "en-US",
        "cashAdvanceAccountCode": "string",
        "testEmployee": true,
        "nonEmployee": true,
        "biManager": {
          "value": "a860a344-d7b2-406e-828e-8d442f23f344",
          "displayName": "string",
          "employeeNumber": "string",
          "$ref": "http://example.com"
        },
        "customData": [
          {
            "id": "custom1",
            "value": "string"
          }
        ]
      },
      "urn:ietf:params:scim:schemas:extension:spend:2.0:Approver": {
        "report": [
          {
            "approver": {
              "value": "a860a344-d7b2-406e-828e-8d442f23f344",
              "displayName": "string",
              "employeeNumber": "string",
              "$ref": "http://example.com"
            },
            "primary": true
          }
        ],
        "cashAdvance": [
          {
            "approver": {
              "value": "a860a344-d7b2-406e-828e-8d442f23f344",
              "displayName": "string",
              "employeeNumber": "string",
              "$ref": "http://example.com"
            },
            "primary": true
          }
        ],
        "request": [
          {
            "approver": {
              "value": "a860a344-d7b2-406e-828e-8d442f23f344",
              "displayName": "string",
              "employeeNumber": "string",
              "$ref": "http://example.com"
            },
            "primary": true
          }
        ],
        "invoice": [
          {
            "approver": {
              "value": "a860a344-d7b2-406e-828e-8d442f23f344",
              "displayName": "string",
              "employeeNumber": "string",
              "$ref": "http://example.com"
            },
            "primary": true
          }
        ],
        "purchaseRequest": [
          {
            "approver": {
              "value": "a860a344-d7b2-406e-828e-8d442f23f344",
              "displayName": "string",
              "employeeNumber": "string",
              "$ref": "http://example.com"
            },
            "primary": true
          }
        ],
        "statement": [
          {
            "approver": {
              "value": "a860a344-d7b2-406e-828e-8d442f23f344",
              "displayName": "string",
              "employeeNumber": "string",
              "$ref": "http://example.com"
            },
            "primary": true
          }
        ],
        "budget": [
          {
            "approver": {
              "value": "a860a344-d7b2-406e-828e-8d442f23f344",
              "displayName": "string",
              "employeeNumber": "string",
              "$ref": "http://example.com"
            },
            "primary": true
          }
        ]
      },
      "urn:ietf:params:scim:schemas:extension:spend:2.0:Delegate": {
        "expense": [
          {
            "canApprove": true,
            "canPrepare": true,
            "canPrepareForApproval": true,
            "canReceiveApprovalEmail": true,
            "canReceiveEmail": true,
            "canSubmit": true,
            "canSubmitTravelRequest": true,
            "canUseBi": true,
            "canViewReceipt": true,
            "delegate": {
              "value": "a860a344-d7b2-406e-828e-8d442f23f344",
              "displayName": "string",
              "employeeNumber": "string",
              "$ref": "http://example.com"
            },
            "temporaryDelegation": {
              "temporaryDelegationFromDate": "2020-09-20T22:35:36.532Z",
              "temporaryDelegationToDate": "2020-12-20T22:35:36.532Z"
            }
          }
        ],
        "payment": [
          {
            "canApprove": true,
            "canPrepare": true,
            "canPrepareForApproval": true,
            "canReceiveApprovalEmail": true,
            "canReceiveEmail": true,
            "canSubmit": true,
            "canSubmitTravelRequest": true,
            "canUseBi": true,
            "canViewReceipt": true,
            "delegate": {
              "value": "a860a344-d7b2-406e-828e-8d442f23f344",
              "displayName": "string",
              "employeeNumber": "string",
              "$ref": "http://example.com"
            },
            "temporaryDelegation": {
              "temporaryDelegationFromDate": "2020-09-20T22:35:36.532Z",
              "temporaryDelegationToDate": "2020-12-20T22:35:36.532Z"
            }
          }
        ],
        "purchaseRequest": [
          {
            "canApprove": true,
            "canPrepare": true,
            "canPrepareForApproval": true,
            "canReceiveApprovalEmail": true,
            "canReceiveEmail": true,
            "canSubmit": true,
            "canSubmitTravelRequest": true,
            "canUseBi": true,
            "canViewReceipt": true,
            "delegate": {
              "value": "a860a344-d7b2-406e-828e-8d442f23f344",
              "displayName": "string",
              "employeeNumber": "string",
              "$ref": "http://example.com"
            },
            "temporaryDelegation": {
              "temporaryDelegationFromDate": "2020-09-20T22:35:36.532Z",
              "temporaryDelegationToDate": "2020-12-20T22:35:36.532Z"
            }
          }
        ]
      },
      "urn:ietf:params:scim:schemas:extension:spend:2.0:Role": {
        "roles": [
          {
            "roleName": "EXP_FB_TAX_ADMIN",
            "roleGroups": [
              "string"
            ]
          }
        ]
      },
      "urn:ietf:params:scim:schemas:extension:spend:2.0:UserPreference": {
        "showImagingIntro": true,
        "expenseAuditRequired": "REQUIRED",
        "allowCreditCardTransArrivalEmails": true,
        "allowReceiptImageAvailEmails": true,
        "promptForCardTransactionsOnReport": true,
        "autoAddTripCardTransOnReport": true,
        "promptForReportPrintFormat": false,
        "defaultReportPrintFormat": "DETAILED",
        "showTotalOnReport": true,
        "showExpenseOnReport": "ALL",
        "showInstructHelpPanel": true,
        "useQuickItinAsDefault": true,
        "allowAutoCreateTripReport": true
      },
      "urn:ietf:params:scim:schemas:extension:enterprise:2.0:Payroll": {
        "adp": {
          "companyCode": "string",
          "deductionCode": "string",
          "employeeFileNumber": "string"
        }
      },
      "urn:ietf:params:scim:schemas:extension:spend:2.0:WorkflowPreference": {
        "emailStatusChangeOnCashAdvance": true,
        "emailAwaitApprovalOnCashAdvance": true,
        "emailStatusChangeOnReport": true,
        "emailAwaitApprovalOnReport": true,
        "promptForApproverOnReportSubmit": true,
        "emailStatusChangeOnTravelRequest": true,
        "emailAwaitApprovalOnTravelRequest": true,
        "promptForApproverOnTravelRequestSubmit": true,
        "emailStatusChangeOnPayment": true,
        "emailAwaitApprovalOnPayment": true,
        "promptForApproverOnPaymentSubmit": true
      }
    }
  ],
  "startIndex": 0,
  "itemsPerPage": 0
}
```

<h3 id="getspendusers-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[ListResponse](#schemalistresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Invalid Request|[ErrorMessageResponse](#schemaerrormessageresponse)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|UnAuthorized|[ErrorMessageResponse](#schemaerrormessageresponse)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[ErrorMessageResponse](#schemaerrormessageresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|User Not Found|[ErrorMessageResponse](#schemaerrormessageresponse)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Error|[ErrorMessageResponse](#schemaerrormessageresponse)|
|501|[Not Implemented](https://tools.ietf.org/html/rfc7231#section-6.6.2)|Not Implemented|[ErrorMessageResponse](#schemaerrormessageresponse)|

<aside class="success">
This operation does not require authentication
</aside>

# Schemas

<h2 id="tocS_Meta">Meta</h2>
<!-- backwards compatibility -->
<a id="schemameta"></a>
<a id="schema_Meta"></a>
<a id="tocSmeta"></a>
<a id="tocsmeta"></a>

```json
{
  "resourceType": "string",
  "created": "2019-08-24T14:15:22Z",
  "lastModified": "2019-08-24T14:15:22Z",
  "location": "http://example.com",
  "version": "string"
}

```

SCIM 2.0 Meta Information

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|resourceType|string|false|none|The resource Type|
|created|string(date-time)|false|none|Date and time the resource was created|
|lastModified|string(date-time)|false|none|Date and time the resource was last modified|
|location|string(uri)|false|none|The location (URI) of the resource|
|version|string|false|none|The version of the resource|

<h2 id="tocS_SpendDelegate">SpendDelegate</h2>
<!-- backwards compatibility -->
<a id="schemaspenddelegate"></a>
<a id="schema_SpendDelegate"></a>
<a id="tocSspenddelegate"></a>
<a id="tocsspenddelegate"></a>

```json
{
  "canApprove": true,
  "canPrepare": true,
  "canPrepareForApproval": true,
  "canReceiveApprovalEmail": true,
  "canReceiveEmail": true,
  "canSubmit": true,
  "canSubmitTravelRequest": true,
  "canUseBi": true,
  "canViewReceipt": true,
  "delegate": {
    "value": "a860a344-d7b2-406e-828e-8d442f23f344",
    "displayName": "string",
    "employeeNumber": "string",
    "$ref": "http://example.com"
  },
  "temporaryDelegation": {
    "temporaryDelegationFromDate": "2020-09-20T22:35:36.532Z",
    "temporaryDelegationToDate": "2020-12-20T22:35:36.532Z"
  }
}

```

The user's spend delegate information

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|canApprove|boolean|false|none|Determines if delegate can approve|
|canPrepare|boolean|false|none|Determines if delegate can prepare|
|canPrepareForApproval|boolean|false|none|Determines if delegate can prepare for approval|
|canReceiveApprovalEmail|boolean|false|none|Determines if delegate can receive approval emails|
|canReceiveEmail|boolean|false|none|Determines if delegate can receive emails|
|canSubmit|boolean|false|none|Determines if delegate can submit|
|canSubmitTravelRequest|boolean|false|none|Determines if delegate can submit travel request|
|canUseBi|boolean|false|none|Determines if delegate can use BI|
|canViewReceipt|boolean|false|none|Determines if delegate can view receipts|
|delegate|[UserReference](#schemauserreference)|false|none|Reference information for a user within the system|
|temporaryDelegation|[TemporaryDelegate](#schematemporarydelegate)|false|none|Determines if delegate can temporarily approve|

<h2 id="tocS_Adp">Adp</h2>
<!-- backwards compatibility -->
<a id="schemaadp"></a>
<a id="schema_Adp"></a>
<a id="tocSadp"></a>
<a id="tocsadp"></a>

```json
{
  "companyCode": "string",
  "deductionCode": "string",
  "employeeFileNumber": "string"
}

```

A user's ADP settings

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|companyCode|string|true|none|The company code for the employee within ADP.|
|deductionCode|string|true|none|The deduction code for the employee within ADP.|
|employeeFileNumber|string|true|none|The identifier for the employee within ADP, also known as the "Employee File Number".|

<h2 id="tocS_ListResponse">ListResponse</h2>
<!-- backwards compatibility -->
<a id="schemalistresponse"></a>
<a id="schema_ListResponse"></a>
<a id="tocSlistresponse"></a>
<a id="tocslistresponse"></a>

```json
{
  "id": "string",
  "externalId": "string",
  "meta": {
    "resourceType": "string",
    "created": "2019-08-24T14:15:22Z",
    "lastModified": "2019-08-24T14:15:22Z",
    "location": "http://example.com",
    "version": "string"
  },
  "totalResults": 0,
  "Resources": [
    {
      "schemas": [
        "string"
      ],
      "externalId": "string",
      "meta": {
        "resourceType": "string",
        "created": "2019-08-24T14:15:22Z",
        "lastModified": "2019-08-24T14:15:22Z",
        "location": "http://example.com",
        "version": "string"
      },
      "urn:ietf:params:scim:schemas:extension:spend:2.0:User": {
        "reimbursementCurrency": "USD",
        "reimbursementType": "ADP_PAYROLL",
        "ledgerCode": "DEFAULT",
        "country": "US",
        "budgetCountryCode": "US",
        "stateProvince": "WA",
        "locale": "en-US",
        "cashAdvanceAccountCode": "string",
        "testEmployee": true,
        "nonEmployee": true,
        "biManager": {
          "value": "a860a344-d7b2-406e-828e-8d442f23f344",
          "displayName": "string",
          "employeeNumber": "string",
          "$ref": "http://example.com"
        },
        "customData": [
          {
            "id": "custom1",
            "value": "string"
          }
        ]
      },
      "urn:ietf:params:scim:schemas:extension:spend:2.0:Approver": {
        "report": [
          {
            "approver": {
              "value": "a860a344-d7b2-406e-828e-8d442f23f344",
              "displayName": "string",
              "employeeNumber": "string",
              "$ref": "http://example.com"
            },
            "primary": true
          }
        ],
        "cashAdvance": [
          {
            "approver": {
              "value": "a860a344-d7b2-406e-828e-8d442f23f344",
              "displayName": "string",
              "employeeNumber": "string",
              "$ref": "http://example.com"
            },
            "primary": true
          }
        ],
        "request": [
          {
            "approver": {
              "value": "a860a344-d7b2-406e-828e-8d442f23f344",
              "displayName": "string",
              "employeeNumber": "string",
              "$ref": "http://example.com"
            },
            "primary": true
          }
        ],
        "invoice": [
          {
            "approver": {
              "value": "a860a344-d7b2-406e-828e-8d442f23f344",
              "displayName": "string",
              "employeeNumber": "string",
              "$ref": "http://example.com"
            },
            "primary": true
          }
        ],
        "purchaseRequest": [
          {
            "approver": {
              "value": "a860a344-d7b2-406e-828e-8d442f23f344",
              "displayName": "string",
              "employeeNumber": "string",
              "$ref": "http://example.com"
            },
            "primary": true
          }
        ],
        "statement": [
          {
            "approver": {
              "value": "a860a344-d7b2-406e-828e-8d442f23f344",
              "displayName": "string",
              "employeeNumber": "string",
              "$ref": "http://example.com"
            },
            "primary": true
          }
        ],
        "budget": [
          {
            "approver": {
              "value": "a860a344-d7b2-406e-828e-8d442f23f344",
              "displayName": "string",
              "employeeNumber": "string",
              "$ref": "http://example.com"
            },
            "primary": true
          }
        ]
      },
      "urn:ietf:params:scim:schemas:extension:spend:2.0:Delegate": {
        "expense": [
          {
            "canApprove": true,
            "canPrepare": true,
            "canPrepareForApproval": true,
            "canReceiveApprovalEmail": true,
            "canReceiveEmail": true,
            "canSubmit": true,
            "canSubmitTravelRequest": true,
            "canUseBi": true,
            "canViewReceipt": true,
            "delegate": {
              "value": "a860a344-d7b2-406e-828e-8d442f23f344",
              "displayName": "string",
              "employeeNumber": "string",
              "$ref": "http://example.com"
            },
            "temporaryDelegation": {
              "temporaryDelegationFromDate": "2020-09-20T22:35:36.532Z",
              "temporaryDelegationToDate": "2020-12-20T22:35:36.532Z"
            }
          }
        ],
        "payment": [
          {
            "canApprove": true,
            "canPrepare": true,
            "canPrepareForApproval": true,
            "canReceiveApprovalEmail": true,
            "canReceiveEmail": true,
            "canSubmit": true,
            "canSubmitTravelRequest": true,
            "canUseBi": true,
            "canViewReceipt": true,
            "delegate": {
              "value": "a860a344-d7b2-406e-828e-8d442f23f344",
              "displayName": "string",
              "employeeNumber": "string",
              "$ref": "http://example.com"
            },
            "temporaryDelegation": {
              "temporaryDelegationFromDate": "2020-09-20T22:35:36.532Z",
              "temporaryDelegationToDate": "2020-12-20T22:35:36.532Z"
            }
          }
        ],
        "purchaseRequest": [
          {
            "canApprove": true,
            "canPrepare": true,
            "canPrepareForApproval": true,
            "canReceiveApprovalEmail": true,
            "canReceiveEmail": true,
            "canSubmit": true,
            "canSubmitTravelRequest": true,
            "canUseBi": true,
            "canViewReceipt": true,
            "delegate": {
              "value": "a860a344-d7b2-406e-828e-8d442f23f344",
              "displayName": "string",
              "employeeNumber": "string",
              "$ref": "http://example.com"
            },
            "temporaryDelegation": {
              "temporaryDelegationFromDate": "2020-09-20T22:35:36.532Z",
              "temporaryDelegationToDate": "2020-12-20T22:35:36.532Z"
            }
          }
        ]
      },
      "urn:ietf:params:scim:schemas:extension:spend:2.0:Role": {
        "roles": [
          {
            "roleName": "EXP_FB_TAX_ADMIN",
            "roleGroups": [
              "string"
            ]
          }
        ]
      },
      "urn:ietf:params:scim:schemas:extension:spend:2.0:UserPreference": {
        "showImagingIntro": true,
        "expenseAuditRequired": "REQUIRED",
        "allowCreditCardTransArrivalEmails": true,
        "allowReceiptImageAvailEmails": true,
        "promptForCardTransactionsOnReport": true,
        "autoAddTripCardTransOnReport": true,
        "promptForReportPrintFormat": false,
        "defaultReportPrintFormat": "DETAILED",
        "showTotalOnReport": true,
        "showExpenseOnReport": "ALL",
        "showInstructHelpPanel": true,
        "useQuickItinAsDefault": true,
        "allowAutoCreateTripReport": true
      },
      "urn:ietf:params:scim:schemas:extension:enterprise:2.0:Payroll": {
        "adp": {
          "companyCode": "string",
          "deductionCode": "string",
          "employeeFileNumber": "string"
        }
      },
      "urn:ietf:params:scim:schemas:extension:spend:2.0:WorkflowPreference": {
        "emailStatusChangeOnCashAdvance": true,
        "emailAwaitApprovalOnCashAdvance": true,
        "emailStatusChangeOnReport": true,
        "emailAwaitApprovalOnReport": true,
        "promptForApproverOnReportSubmit": true,
        "emailStatusChangeOnTravelRequest": true,
        "emailAwaitApprovalOnTravelRequest": true,
        "promptForApproverOnTravelRequestSubmit": true,
        "emailStatusChangeOnPayment": true,
        "emailAwaitApprovalOnPayment": true,
        "promptForApproverOnPaymentSubmit": true
      }
    }
  ],
  "startIndex": 0,
  "itemsPerPage": 0
}

```

A paginated list of SCIM resources

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string|false|none|The id for the SCIM resource|
|externalId|string|false|none|The external id for the SCIM resource|
|meta|[Meta](#schemameta)|false|none|SCIM 2.0 Meta Information|
|totalResults|integer(int32)|true|none|The total number of results returned by the list or query operation|
|Resources|[[FullSpendUser](#schemafullspenduser)]|true|none|A multi-valued list of complex objects containing the requested resources|
|startIndex|integer(int32)|false|none|The 1-based index of the first result in the current set of list results|
|itemsPerPage|integer(int32)|false|none|The number of resources returned in a list response page|

<h2 id="tocS_SpendApprover">SpendApprover</h2>
<!-- backwards compatibility -->
<a id="schemaspendapprover"></a>
<a id="schema_SpendApprover"></a>
<a id="tocSspendapprover"></a>
<a id="tocsspendapprover"></a>

```json
{
  "approver": {
    "value": "a860a344-d7b2-406e-828e-8d442f23f344",
    "displayName": "string",
    "employeeNumber": "string",
    "$ref": "http://example.com"
  },
  "primary": true
}

```

The user's spend approver information

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|approver|[UserReference](#schemauserreference)|true|none|Reference information for a user within the system|
|primary|boolean|true|none|The value for indicating whether the associated user is primary approver|

<h2 id="tocS_FullSpendUser">FullSpendUser</h2>
<!-- backwards compatibility -->
<a id="schemafullspenduser"></a>
<a id="schema_FullSpendUser"></a>
<a id="tocSfullspenduser"></a>
<a id="tocsfullspenduser"></a>

```json
{
  "schemas": [
    "string"
  ],
  "externalId": "string",
  "meta": {
    "resourceType": "string",
    "created": "2019-08-24T14:15:22Z",
    "lastModified": "2019-08-24T14:15:22Z",
    "location": "http://example.com",
    "version": "string"
  },
  "urn:ietf:params:scim:schemas:extension:spend:2.0:User": {
    "reimbursementCurrency": "USD",
    "reimbursementType": "ADP_PAYROLL",
    "ledgerCode": "DEFAULT",
    "country": "US",
    "budgetCountryCode": "US",
    "stateProvince": "WA",
    "locale": "en-US",
    "cashAdvanceAccountCode": "string",
    "testEmployee": true,
    "nonEmployee": true,
    "biManager": {
      "value": "a860a344-d7b2-406e-828e-8d442f23f344",
      "displayName": "string",
      "employeeNumber": "string",
      "$ref": "http://example.com"
    },
    "customData": [
      {
        "id": "custom1",
        "value": "string"
      }
    ]
  },
  "urn:ietf:params:scim:schemas:extension:spend:2.0:Approver": {
    "report": [
      {
        "approver": {
          "value": "a860a344-d7b2-406e-828e-8d442f23f344",
          "displayName": "string",
          "employeeNumber": "string",
          "$ref": "http://example.com"
        },
        "primary": true
      }
    ],
    "cashAdvance": [
      {
        "approver": {
          "value": "a860a344-d7b2-406e-828e-8d442f23f344",
          "displayName": "string",
          "employeeNumber": "string",
          "$ref": "http://example.com"
        },
        "primary": true
      }
    ],
    "request": [
      {
        "approver": {
          "value": "a860a344-d7b2-406e-828e-8d442f23f344",
          "displayName": "string",
          "employeeNumber": "string",
          "$ref": "http://example.com"
        },
        "primary": true
      }
    ],
    "invoice": [
      {
        "approver": {
          "value": "a860a344-d7b2-406e-828e-8d442f23f344",
          "displayName": "string",
          "employeeNumber": "string",
          "$ref": "http://example.com"
        },
        "primary": true
      }
    ],
    "purchaseRequest": [
      {
        "approver": {
          "value": "a860a344-d7b2-406e-828e-8d442f23f344",
          "displayName": "string",
          "employeeNumber": "string",
          "$ref": "http://example.com"
        },
        "primary": true
      }
    ],
    "statement": [
      {
        "approver": {
          "value": "a860a344-d7b2-406e-828e-8d442f23f344",
          "displayName": "string",
          "employeeNumber": "string",
          "$ref": "http://example.com"
        },
        "primary": true
      }
    ],
    "budget": [
      {
        "approver": {
          "value": "a860a344-d7b2-406e-828e-8d442f23f344",
          "displayName": "string",
          "employeeNumber": "string",
          "$ref": "http://example.com"
        },
        "primary": true
      }
    ]
  },
  "urn:ietf:params:scim:schemas:extension:spend:2.0:Delegate": {
    "expense": [
      {
        "canApprove": true,
        "canPrepare": true,
        "canPrepareForApproval": true,
        "canReceiveApprovalEmail": true,
        "canReceiveEmail": true,
        "canSubmit": true,
        "canSubmitTravelRequest": true,
        "canUseBi": true,
        "canViewReceipt": true,
        "delegate": {
          "value": "a860a344-d7b2-406e-828e-8d442f23f344",
          "displayName": "string",
          "employeeNumber": "string",
          "$ref": "http://example.com"
        },
        "temporaryDelegation": {
          "temporaryDelegationFromDate": "2020-09-20T22:35:36.532Z",
          "temporaryDelegationToDate": "2020-12-20T22:35:36.532Z"
        }
      }
    ],
    "payment": [
      {
        "canApprove": true,
        "canPrepare": true,
        "canPrepareForApproval": true,
        "canReceiveApprovalEmail": true,
        "canReceiveEmail": true,
        "canSubmit": true,
        "canSubmitTravelRequest": true,
        "canUseBi": true,
        "canViewReceipt": true,
        "delegate": {
          "value": "a860a344-d7b2-406e-828e-8d442f23f344",
          "displayName": "string",
          "employeeNumber": "string",
          "$ref": "http://example.com"
        },
        "temporaryDelegation": {
          "temporaryDelegationFromDate": "2020-09-20T22:35:36.532Z",
          "temporaryDelegationToDate": "2020-12-20T22:35:36.532Z"
        }
      }
    ],
    "purchaseRequest": [
      {
        "canApprove": true,
        "canPrepare": true,
        "canPrepareForApproval": true,
        "canReceiveApprovalEmail": true,
        "canReceiveEmail": true,
        "canSubmit": true,
        "canSubmitTravelRequest": true,
        "canUseBi": true,
        "canViewReceipt": true,
        "delegate": {
          "value": "a860a344-d7b2-406e-828e-8d442f23f344",
          "displayName": "string",
          "employeeNumber": "string",
          "$ref": "http://example.com"
        },
        "temporaryDelegation": {
          "temporaryDelegationFromDate": "2020-09-20T22:35:36.532Z",
          "temporaryDelegationToDate": "2020-12-20T22:35:36.532Z"
        }
      }
    ]
  },
  "urn:ietf:params:scim:schemas:extension:spend:2.0:Role": {
    "roles": [
      {
        "roleName": "EXP_FB_TAX_ADMIN",
        "roleGroups": [
          "string"
        ]
      }
    ]
  },
  "urn:ietf:params:scim:schemas:extension:spend:2.0:UserPreference": {
    "showImagingIntro": true,
    "expenseAuditRequired": "REQUIRED",
    "allowCreditCardTransArrivalEmails": true,
    "allowReceiptImageAvailEmails": true,
    "promptForCardTransactionsOnReport": true,
    "autoAddTripCardTransOnReport": true,
    "promptForReportPrintFormat": false,
    "defaultReportPrintFormat": "DETAILED",
    "showTotalOnReport": true,
    "showExpenseOnReport": "ALL",
    "showInstructHelpPanel": true,
    "useQuickItinAsDefault": true,
    "allowAutoCreateTripReport": true
  },
  "urn:ietf:params:scim:schemas:extension:enterprise:2.0:Payroll": {
    "adp": {
      "companyCode": "string",
      "deductionCode": "string",
      "employeeFileNumber": "string"
    }
  },
  "urn:ietf:params:scim:schemas:extension:spend:2.0:WorkflowPreference": {
    "emailStatusChangeOnCashAdvance": true,
    "emailAwaitApprovalOnCashAdvance": true,
    "emailStatusChangeOnReport": true,
    "emailAwaitApprovalOnReport": true,
    "promptForApproverOnReportSubmit": true,
    "emailStatusChangeOnTravelRequest": true,
    "emailAwaitApprovalOnTravelRequest": true,
    "promptForApproverOnTravelRequestSubmit": true,
    "emailStatusChangeOnPayment": true,
    "emailAwaitApprovalOnPayment": true,
    "promptForApproverOnPaymentSubmit": true
  }
}

```

All spend SCIM resources for a given user

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|schemas|[string]|false|none|none|
|externalId|string|false|none|none|
|meta|[Meta](#schemameta)|false|none|SCIM 2.0 Meta Information|
|urn:ietf:params:scim:schemas:extension:spend:2.0:User|[SpendUser](#schemaspenduser)|false|none|A user's base spend information|
|urn:ietf:params:scim:schemas:extension:spend:2.0:Approver|[ApproverExtension](#schemaapproverextension)|false|none|A user's spend approvers|
|urn:ietf:params:scim:schemas:extension:spend:2.0:Delegate|[DelegateExtension](#schemadelegateextension)|false|none|A user's spend delegate information|
|urn:ietf:params:scim:schemas:extension:spend:2.0:Role|[SpendRole](#schemaspendrole)|false|none|A user's spend roles|
|urn:ietf:params:scim:schemas:extension:spend:2.0:UserPreference|[UserPreferenceExtension](#schemauserpreferenceextension)|false|none|A user's spend preferences|
|urn:ietf:params:scim:schemas:extension:enterprise:2.0:Payroll|[AdpExtension](#schemaadpextension)|false|none|none|
|urn:ietf:params:scim:schemas:extension:spend:2.0:WorkflowPreference|[WorkflowPreferenceExtension](#schemaworkflowpreferenceextension)|false|none|A user's spend workflow preference settings|

<h2 id="tocS_ApproverExtension">ApproverExtension</h2>
<!-- backwards compatibility -->
<a id="schemaapproverextension"></a>
<a id="schema_ApproverExtension"></a>
<a id="tocSapproverextension"></a>
<a id="tocsapproverextension"></a>

```json
{
  "report": [
    {
      "approver": {
        "value": "a860a344-d7b2-406e-828e-8d442f23f344",
        "displayName": "string",
        "employeeNumber": "string",
        "$ref": "http://example.com"
      },
      "primary": true
    }
  ],
  "cashAdvance": [
    {
      "approver": {
        "value": "a860a344-d7b2-406e-828e-8d442f23f344",
        "displayName": "string",
        "employeeNumber": "string",
        "$ref": "http://example.com"
      },
      "primary": true
    }
  ],
  "request": [
    {
      "approver": {
        "value": "a860a344-d7b2-406e-828e-8d442f23f344",
        "displayName": "string",
        "employeeNumber": "string",
        "$ref": "http://example.com"
      },
      "primary": true
    }
  ],
  "invoice": [
    {
      "approver": {
        "value": "a860a344-d7b2-406e-828e-8d442f23f344",
        "displayName": "string",
        "employeeNumber": "string",
        "$ref": "http://example.com"
      },
      "primary": true
    }
  ],
  "purchaseRequest": [
    {
      "approver": {
        "value": "a860a344-d7b2-406e-828e-8d442f23f344",
        "displayName": "string",
        "employeeNumber": "string",
        "$ref": "http://example.com"
      },
      "primary": true
    }
  ],
  "statement": [
    {
      "approver": {
        "value": "a860a344-d7b2-406e-828e-8d442f23f344",
        "displayName": "string",
        "employeeNumber": "string",
        "$ref": "http://example.com"
      },
      "primary": true
    }
  ],
  "budget": [
    {
      "approver": {
        "value": "a860a344-d7b2-406e-828e-8d442f23f344",
        "displayName": "string",
        "employeeNumber": "string",
        "$ref": "http://example.com"
      },
      "primary": true
    }
  ]
}

```

A user's spend approvers

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|report|[[SpendApprover](#schemaspendapprover)]|false|none|[The user's spend approver information]|
|cashAdvance|[[SpendApprover](#schemaspendapprover)]|false|none|[The user's spend approver information]|
|request|[[SpendApprover](#schemaspendapprover)]|false|none|[The user's spend approver information]|
|invoice|[[SpendApprover](#schemaspendapprover)]|false|none|[The user's spend approver information]|
|purchaseRequest|[[SpendApprover](#schemaspendapprover)]|false|none|[The user's spend approver information]|
|statement|[[SpendApprover](#schemaspendapprover)]|false|none|[The user's spend approver information]|
|budget|[[SpendApprover](#schemaspendapprover)]|false|none|[The user's spend approver information]|

<h2 id="tocS_ErrorMessageResponse">ErrorMessageResponse</h2>
<!-- backwards compatibility -->
<a id="schemaerrormessageresponse"></a>
<a id="schema_ErrorMessageResponse"></a>
<a id="tocSerrormessageresponse"></a>
<a id="tocserrormessageresponse"></a>

```json
{
  "schemas": [
    "string"
  ],
  "id": "string",
  "externalId": "string",
  "meta": {
    "resourceType": "string",
    "created": "2019-08-24T14:15:22Z",
    "lastModified": "2019-08-24T14:15:22Z",
    "location": "http://example.com",
    "version": "string"
  },
  "scimType": "string",
  "detail": "string",
  "status": 0
}

```

The error response object

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|schemas|[string]|false|none|The schemas present in this resource|
|id|string|false|none|The Id of the resource|
|externalId|string|false|none|The external Id of the resource|
|meta|[Meta](#schemameta)|false|none|SCIM 2.0 Meta Information|
|scimType|string|false|none|A SCIM detailed error keyword.|
|detail|string|false|none|A detailed, human readable message.|
|status|integer(int32)|false|none|The HTTP status code.|

<h2 id="tocS_UserReference">UserReference</h2>
<!-- backwards compatibility -->
<a id="schemauserreference"></a>
<a id="schema_UserReference"></a>
<a id="tocSuserreference"></a>
<a id="tocsuserreference"></a>

```json
{
  "value": "a860a344-d7b2-406e-828e-8d442f23f344",
  "displayName": "string",
  "employeeNumber": "string",
  "$ref": "http://example.com"
}

```

Reference information for a user within the system

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|value|string(uuid)|false|none|The internal UUID identifier for the user|
|displayName|string|false|read-only|The username for the user|
|employeeNumber|string|false|none|The employee number for the user|
|$ref|string(uri)|false|read-only|The URI reference for the user|

<h2 id="tocS_Role">Role</h2>
<!-- backwards compatibility -->
<a id="schemarole"></a>
<a id="schema_Role"></a>
<a id="tocSrole"></a>
<a id="tocsrole"></a>

```json
{
  "roleName": "EXP_FB_TAX_ADMIN",
  "roleGroups": [
    "string"
  ]
}

```

Expense Roles for Employee

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|roleName|string|true|none|Expense Role for Employee|
|roleGroups|[string]|false|none|Group(s) to be associated with the Expense Role|

#### Enumerated Values

|Property|Value|
|---|---|
|roleName|EXP_FB_TAX_ADMIN|
|roleName|EXP_USER|
|roleName|EXP_TRAVEL_AND_EXPENSE_USER|
|roleName|EXP_PROXY_USER|
|roleName|EXP_APPROVER|
|roleName|EXP_CONFIG_ADMIN|
|roleName|EXP_CONFIG_ADMIN_CLIENT|
|roleName|EXP_CONFIG_ADMIN_RO|
|roleName|EXP_EMPLOYEE_ADMIN|
|roleName|EXP_CARD_ADMIN|
|roleName|EXP_CASHADVANCE_ADMIN|
|roleName|EXP_EXTRACT_ADMIN|
|roleName|EXP_PROCESSOR|
|roleName|EXP_PROCESSOR_AUDIT|
|roleName|EXP_PROCESSOR_ADMIN|
|roleName|EXP_PROCESSOR_CR|
|roleName|EXP_ATTENDEE_ADMIN|
|roleName|EXP_ATTENDEE_ADMIN_RO|
|roleName|EXP_REIMBURSEMENT_AUDITOR|
|roleName|EXP_REIMBURSEMENT_APPROVER|
|roleName|EXP_FIND_ATTENDEES_USER|
|roleName|EXP_PCARD_ADMIN|
|roleName|EXP_RECEIPT_PROCESSOR|
|roleName|STATEMENT_PROCESSOR_AUDITOR|
|roleName|STATEMENT_PROCESSOR|
|roleName|STATEMENT_PROCESSOR_ADMIN|
|roleName|STATEMENT_APPROVER|
|roleName|STATEMENT_USER|
|roleName|TRAVEL_USER|
|roleName|INV_PURCH_RECEIVER|
|roleName|INV_EMPLOYEE_ADMIN|
|roleName|INV_IMAGE_PROCESSOR|
|roleName|INV_RECEIPT_PROCESSOR|
|roleName|INV_PMT_MANAGER|
|roleName|INV_PURCH_USER|
|roleName|INV_APPROVER|
|roleName|INV_AP_USER|
|roleName|INV_PROCESSOR_AUDIT|
|roleName|INV_PMT_USER|
|roleName|INV_PROCESSOR|
|roleName|INV_PROCESSOR_MANAGER|
|roleName|INV_CONFIG_ADMIN|
|roleName|INV_CONFIG_ADMIN_RO|
|roleName|INV_IC_VERIFIER|
|roleName|INV_PROXY_USER|
|roleName|INV_TAX_ADMIN|
|roleName|INV_VENDOR_ADMIN|
|roleName|INV_PURCH_ORDER_PROCESSOR_AUDIT|
|roleName|INV_PURCH_ORDER_PROCESSOR|
|roleName|INV_PURCH_REQ_APPROVER|
|roleName|INV_PURCH_REQ_PROCESSOR_AUDIT|
|roleName|INV_PURCH_REQ_PROCESSOR|
|roleName|INV_PURCH_REQ_USER|
|roleName|INV_PURCH_REQ_PROXY_USER|
|roleName|INV_RECEIPT_USER|
|roleName|REQ_CONFIG_ADMIN|
|roleName|REQ_CONFIG_ADMIN_RO|
|roleName|REQ_EVENT_ADMIN|
|roleName|REQ_APPROVER|
|roleName|REQ_PROCESSOR|
|roleName|REQ_PROCESSOR_ADMIN|
|roleName|REQ_PROCESSOR_AUDIT|
|roleName|REQ_PROXY_USER|
|roleName|REQ_USER|
|roleName|REQ_RISK_ADMIN|
|roleName|BUDGET_REPORTING_USER|
|roleName|REPORTING_CONFIG_ADMIN|
|roleName|REPORTING_HIST_DATA_USER|
|roleName|REPORTING_DASHBOARD_USER|
|roleName|REPORTING_EMPLOYEE_ADMIN|
|roleName|REPORTING_CAS_ANALYST|
|roleName|REPORTING_BUSINESS_AUTHOR|
|roleName|REPORTING_CONSUMER|
|roleName|REPORTING_PRO_AUTHOR|
|roleName|SHD_APP_CENTER_ADMIN|
|roleName|SHD_AUTHORIZED_APPROVER|
|roleName|SHD_BUDGET_APPROVER|
|roleName|SHD_BILLING_ATTRIBUTES_USER|
|roleName|SHD_BUDGET_ADMIN|
|roleName|SHD_BUDGET_OWNER|
|roleName|SHD_BUDGET_VIEWER|
|roleName|SHD_COST_OBJECT_APPROVER|
|roleName|SHD_DATA_RETENTION_ADMIN|
|roleName|SHD_COMPANY_INFO_ADMIN|
|roleName|SHD_EMPLOYEE_ADMIN|
|roleName|SHD_EMPLOYEE_ADMIN_RO|
|roleName|SHD_IMPORT_EXTRACT_ADMIN|
|roleName|SHD_IMPORT_EXTRACT_ADMIN_RO|
|roleName|SHD_PASSWORD_ADMIN|
|roleName|SHD_ROLE_ADMIN|
|roleName|SHD_CONFIG_ADMIN|
|roleName|SHD_CONFIG_ADMIN_RO|
|roleName|SHD_TAX_ADMIN|
|roleName|SHD_TAX_ADMIN_RO|
|roleName|SHD_TRAINING_ADMIN|
|roleName|SHD_WEB_SERVICES_ADMIN|

<h2 id="tocS_SpendRole">SpendRole</h2>
<!-- backwards compatibility -->
<a id="schemaspendrole"></a>
<a id="schema_SpendRole"></a>
<a id="tocSspendrole"></a>
<a id="tocsspendrole"></a>

```json
{
  "roles": [
    {
      "roleName": "EXP_FB_TAX_ADMIN",
      "roleGroups": [
        "string"
      ]
    }
  ]
}

```

A user's spend roles

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|roles|[[Role](#schemarole)]|false|none|Expense Roles for Employee|

<h2 id="tocS_WorkflowPreferences">WorkflowPreferences</h2>
<!-- backwards compatibility -->
<a id="schemaworkflowpreferences"></a>
<a id="schema_WorkflowPreferences"></a>
<a id="tocSworkflowpreferences"></a>
<a id="tocsworkflowpreferences"></a>

```json
{
  "id": "string",
  "uuId": "0757149a-1b5d-4494-b3fb-bbf85aad909a",
  "emailOnCaStatusChange": "N, Y",
  "emailOnCaAwaitApproval": "N, Y",
  "emailOnRptStatusChange": "N, Y",
  "emailOnRptAwaitApproval": "N, Y",
  "promptForApproverOnSubmit": "N, Y",
  "emailOnTrStatusChange": "N, Y",
  "emailOnTrAwaitApproval": "N, Y",
  "promptForTrApproverOnSubmit": "N, Y",
  "emailOnPmtStatusChange": "N, Y",
  "emailOnPmtAwaitApproval": "N, Y",
  "promptForPmtApproverOnSubmit": "N, Y"
}

```

A user's spend workflow preferences

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string|true|none|The unique identifier of the input Preferences object|
|uuId|string(uuid)|true|none|User Id as a UUID matches user profile uuid|
|emailOnCaStatusChange|string|false|none|Send email when the cash advance status changes, defaulted to Y|
|emailOnCaAwaitApproval|string|false|none|Send email when a cash advance is awaiting approval, defaulted to Y|
|emailOnRptStatusChange|string|false|none|Send email when the report status changes, defaulted to Y|
|emailOnRptAwaitApproval|string|false|none|Send email when a report is awaiting approval, defaulted to Y|
|promptForApproverOnSubmit|string|false|none|Prompt for approver when submitting a report, defaulted to N|
|emailOnTrStatusChange|string|false|none|Send email when the travel request status changes, defaulted to Y|
|emailOnTrAwaitApproval|string|false|none|Send email when a travel request is awaiting approval, defaulted to Y|
|promptForTrApproverOnSubmit|string|false|none|Prompt for approver when submitting a travel request, defaulted to N|
|emailOnPmtStatusChange|string|false|none|Send email when the payment status changes, defaulted to Y|
|emailOnPmtAwaitApproval|string|false|none|Send email when a payment is awaiting approval, defaulted to Y|
|promptForPmtApproverOnSubmit|string|false|none|Prompt for approver when submitting a payment, defaulted to N|

#### Enumerated Values

|Property|Value|
|---|---|
|emailOnCaStatusChange|N, Y|
|emailOnCaAwaitApproval|N, Y|
|emailOnRptStatusChange|N, Y|
|emailOnRptAwaitApproval|N, Y|
|promptForApproverOnSubmit|N, Y|
|emailOnTrStatusChange|N, Y|
|emailOnTrAwaitApproval|N, Y|
|promptForTrApproverOnSubmit|N, Y|
|emailOnPmtStatusChange|N, Y|
|emailOnPmtAwaitApproval|N, Y|
|promptForPmtApproverOnSubmit|N, Y|

<h2 id="tocS_AdpExtension">AdpExtension</h2>
<!-- backwards compatibility -->
<a id="schemaadpextension"></a>
<a id="schema_AdpExtension"></a>
<a id="tocSadpextension"></a>
<a id="tocsadpextension"></a>

```json
{
  "adp": {
    "companyCode": "string",
    "deductionCode": "string",
    "employeeFileNumber": "string"
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|adp|[Adp](#schemaadp)|false|none|A user's ADP settings|

<h2 id="tocS_UserPreferenceExtension">UserPreferenceExtension</h2>
<!-- backwards compatibility -->
<a id="schemauserpreferenceextension"></a>
<a id="schema_UserPreferenceExtension"></a>
<a id="tocSuserpreferenceextension"></a>
<a id="tocsuserpreferenceextension"></a>

```json
{
  "showImagingIntro": true,
  "expenseAuditRequired": "REQUIRED",
  "allowCreditCardTransArrivalEmails": true,
  "allowReceiptImageAvailEmails": true,
  "promptForCardTransactionsOnReport": true,
  "autoAddTripCardTransOnReport": true,
  "promptForReportPrintFormat": false,
  "defaultReportPrintFormat": "DETAILED",
  "showTotalOnReport": true,
  "showExpenseOnReport": "ALL",
  "showInstructHelpPanel": true,
  "useQuickItinAsDefault": true,
  "allowAutoCreateTripReport": true
}

```

A user's spend preferences

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|showImagingIntro|boolean|false|none|Display imaging introduction, defaulted to true.|
|expenseAuditRequired|string|false|none|Expense Audit is required.|
|allowCreditCardTransArrivalEmails|boolean|false|none|Allow Credit Card Transaction Arrival Notification Emails, defaulted to true.|
|allowReceiptImageAvailEmails|boolean|false|none|Send email when faxed receipts are successfully received, defaulted to true.|
|promptForCardTransactionsOnReport|boolean|false|none|Prompt for Company Card Transactions when creating a new report, defaulted to true.|
|autoAddTripCardTransOnReport|boolean|false|none|Add company card transactions within trip dates to 1 click expense report.|
|promptForReportPrintFormat|boolean|false|none|Always prompt for the report format before printing.|
|defaultReportPrintFormat|string|false|none|Default expense report print type.|
|showTotalOnReport|boolean|false|none|Show Report Totals on Detailed Report.|
|showExpenseOnReport|string|false|none|Show expenses on detailed report.|
|showInstructHelpPanel|boolean|false|none|Display instructional help, defaulted to true.|
|useQuickItinAsDefault|boolean|false|none|Use quick itinerary as default.|
|allowAutoCreateTripReport|boolean|false|none|none|

<h2 id="tocS_SearchRequest">SearchRequest</h2>
<!-- backwards compatibility -->
<a id="schemasearchrequest"></a>
<a id="schema_SearchRequest"></a>
<a id="tocSsearchrequest"></a>
<a id="tocssearchrequest"></a>

```json
{
  "startIndex": 1,
  "itemsPerPage": 100,
  "filter": "urn:ietf:params:scim:schemas:extension:spend:2.0:User:country eq \"US\""
}

```

The parameters with which to filter and paginate requested SCIM resources

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|startIndex|integer(int32)|false|none|The 1-based index of the first result in the current set of list results.|
|itemsPerPage|integer(int32)|false|none|The number of resources returned in a list response page.|
|filter|string|false|none|The filter string used to request a subset of resources. Must follow ABNF syntax rules|

<h2 id="tocS_SpendUser">SpendUser</h2>
<!-- backwards compatibility -->
<a id="schemaspenduser"></a>
<a id="schema_SpendUser"></a>
<a id="tocSspenduser"></a>
<a id="tocsspenduser"></a>

```json
{
  "reimbursementCurrency": "USD",
  "reimbursementType": "ADP_PAYROLL",
  "ledgerCode": "DEFAULT",
  "country": "US",
  "budgetCountryCode": "US",
  "stateProvince": "WA",
  "locale": "en-US",
  "cashAdvanceAccountCode": "string",
  "testEmployee": true,
  "nonEmployee": true,
  "biManager": {
    "value": "a860a344-d7b2-406e-828e-8d442f23f344",
    "displayName": "string",
    "employeeNumber": "string",
    "$ref": "http://example.com"
  },
  "customData": [
    {
      "id": "custom1",
      "value": "string"
    }
  ]
}

```

A user's base spend information

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|reimbursementCurrency|string|true|none|Valid three digit currency code in the list of system reimbursement currencies|
|reimbursementType|string|false|none|The reimbursement type for the user|
|ledgerCode|string|false|none|Ledger code to associate with the user|
|country|string|true|none|Valid ISO 3166 country code|
|budgetCountryCode|string|false|none|Valid ISO 3166 country code for Budget|
|stateProvince|string|false|none|Valid ISO sub country code|
|locale|string|true|none|Valid locale from the list of configured locales as defined in [RFC5646]|
|cashAdvanceAccountCode|string|false|none|Valid cash advance account code|
|testEmployee|boolean|false|none|A Boolean value indicating whether the User is a test user. Can't be modified after the user is created. Can only be set at creation.|
|nonEmployee|boolean|false|none|A Boolean value indicating whether the User is a NonEmployee|
|biManager|[UserReference](#schemauserreference)|false|none|Reference information for a user within the system|
|customData|[[CustomData](#schemacustomdata)]|false|none|[The spend custom data associated to the user]|

#### Enumerated Values

|Property|Value|
|---|---|
|reimbursementType|ACCOUNTS_PAYABLE|
|reimbursementType|ADP_PAYROLL|
|reimbursementType|CONCUR_PAY|
|reimbursementType|OTHER|
|reimbursementType|PAY_PAL|

<h2 id="tocS_DelegateExtension">DelegateExtension</h2>
<!-- backwards compatibility -->
<a id="schemadelegateextension"></a>
<a id="schema_DelegateExtension"></a>
<a id="tocSdelegateextension"></a>
<a id="tocsdelegateextension"></a>

```json
{
  "expense": [
    {
      "canApprove": true,
      "canPrepare": true,
      "canPrepareForApproval": true,
      "canReceiveApprovalEmail": true,
      "canReceiveEmail": true,
      "canSubmit": true,
      "canSubmitTravelRequest": true,
      "canUseBi": true,
      "canViewReceipt": true,
      "delegate": {
        "value": "a860a344-d7b2-406e-828e-8d442f23f344",
        "displayName": "string",
        "employeeNumber": "string",
        "$ref": "http://example.com"
      },
      "temporaryDelegation": {
        "temporaryDelegationFromDate": "2020-09-20T22:35:36.532Z",
        "temporaryDelegationToDate": "2020-12-20T22:35:36.532Z"
      }
    }
  ],
  "payment": [
    {
      "canApprove": true,
      "canPrepare": true,
      "canPrepareForApproval": true,
      "canReceiveApprovalEmail": true,
      "canReceiveEmail": true,
      "canSubmit": true,
      "canSubmitTravelRequest": true,
      "canUseBi": true,
      "canViewReceipt": true,
      "delegate": {
        "value": "a860a344-d7b2-406e-828e-8d442f23f344",
        "displayName": "string",
        "employeeNumber": "string",
        "$ref": "http://example.com"
      },
      "temporaryDelegation": {
        "temporaryDelegationFromDate": "2020-09-20T22:35:36.532Z",
        "temporaryDelegationToDate": "2020-12-20T22:35:36.532Z"
      }
    }
  ],
  "purchaseRequest": [
    {
      "canApprove": true,
      "canPrepare": true,
      "canPrepareForApproval": true,
      "canReceiveApprovalEmail": true,
      "canReceiveEmail": true,
      "canSubmit": true,
      "canSubmitTravelRequest": true,
      "canUseBi": true,
      "canViewReceipt": true,
      "delegate": {
        "value": "a860a344-d7b2-406e-828e-8d442f23f344",
        "displayName": "string",
        "employeeNumber": "string",
        "$ref": "http://example.com"
      },
      "temporaryDelegation": {
        "temporaryDelegationFromDate": "2020-09-20T22:35:36.532Z",
        "temporaryDelegationToDate": "2020-12-20T22:35:36.532Z"
      }
    }
  ]
}

```

A user's spend delegate information

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|expense|[[SpendDelegate](#schemaspenddelegate)]|false|none|A list of expense delegates|
|payment|[[SpendDelegate](#schemaspenddelegate)]|false|none|A list of payment delegates|
|purchaseRequest|[[SpendDelegate](#schemaspenddelegate)]|false|none|A list of purchase request delegates|

<h2 id="tocS_CustomData">CustomData</h2>
<!-- backwards compatibility -->
<a id="schemacustomdata"></a>
<a id="schema_CustomData"></a>
<a id="tocScustomdata"></a>
<a id="tocscustomdata"></a>

```json
{
  "id": "custom1",
  "value": "string"
}

```

The spend custom data associated to the user

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string|false|none|custom1 - custom22, orgUnit1 - orgUnit6|
|value|string|false|none|Value of the custom field - For list = List Item Code|

<h2 id="tocS_TemporaryDelegate">TemporaryDelegate</h2>
<!-- backwards compatibility -->
<a id="schematemporarydelegate"></a>
<a id="schema_TemporaryDelegate"></a>
<a id="tocStemporarydelegate"></a>
<a id="tocstemporarydelegate"></a>

```json
{
  "temporaryDelegationFromDate": "2020-09-20T22:35:36.532Z",
  "temporaryDelegationToDate": "2020-12-20T22:35:36.532Z"
}

```

Determines if delegate can temporarily approve

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|temporaryDelegationFromDate|string|false|none|Start date for delegates temporary approval permissions. Valid ISO 8601 Date|
|temporaryDelegationToDate|string|false|none|End date for delegates temporary approval permissions. Valid ISO 8601 Date|

<h2 id="tocS_WorkflowPreferenceExtension">WorkflowPreferenceExtension</h2>
<!-- backwards compatibility -->
<a id="schemaworkflowpreferenceextension"></a>
<a id="schema_WorkflowPreferenceExtension"></a>
<a id="tocSworkflowpreferenceextension"></a>
<a id="tocsworkflowpreferenceextension"></a>

```json
{
  "emailStatusChangeOnCashAdvance": true,
  "emailAwaitApprovalOnCashAdvance": true,
  "emailStatusChangeOnReport": true,
  "emailAwaitApprovalOnReport": true,
  "promptForApproverOnReportSubmit": true,
  "emailStatusChangeOnTravelRequest": true,
  "emailAwaitApprovalOnTravelRequest": true,
  "promptForApproverOnTravelRequestSubmit": true,
  "emailStatusChangeOnPayment": true,
  "emailAwaitApprovalOnPayment": true,
  "promptForApproverOnPaymentSubmit": true
}

```

A user's spend workflow preference settings

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|emailStatusChangeOnCashAdvance|boolean|false|none|Send email when the cash advance status changes, defaulted to true.|
|emailAwaitApprovalOnCashAdvance|boolean|false|none|Send email when a cash advance is awaiting approval, defaulted to true.|
|emailStatusChangeOnReport|boolean|false|none|Send email when the report status changes, defaulted to true.|
|emailAwaitApprovalOnReport|boolean|false|none|Send email when a report is awaiting approval, defaulted to true.|
|promptForApproverOnReportSubmit|boolean|false|none|Prompt for approver when submitting a report, defaulted to false.|
|emailStatusChangeOnTravelRequest|boolean|false|none|Send email when the travel request status changes, defaulted to true.|
|emailAwaitApprovalOnTravelRequest|boolean|false|none|Send email when a travel request is awaiting approval, defaulted to true.|
|promptForApproverOnTravelRequestSubmit|boolean|false|none|Prompt for approver when submitting a travel request, defaulted to false.|
|emailStatusChangeOnPayment|boolean|false|none|Send email when the payment status changes, defaulted to true.|
|emailAwaitApprovalOnPayment|boolean|false|none|Send email when a payment is awaiting approval, defaulted to true.|
|promptForApproverOnPaymentSubmit|boolean|false|none|Prompt for approver when submitting a payment, defaulted to false.|

