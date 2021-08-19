<!-- Generator: Widdershins v4.0.1 -->

<h1 id="itinerary-api">Itinerary API v4</h1>

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

This is the api specification for the Itinerary API.

Introduction
The Itinerary API provides clients and authorized partners access to travel itinerary data. They can now subscribe to events and fetch trips by ID.

Base URLs:

* <a href="https://us.api.concursolutions.com/travel/v4">https://us.api.concursolutions.com/travel/v4</a>

<a href="http://us.api.concursolutions.com/terms">Terms of service</a>

License: <a href="https://developer.concur.com/Terms-of-Use.html">Concur</a>

<h1 id="itinerary-api-trip">trip</h1>

## get__trips_{tripID}

> Code samples

```shell
# You can also use wget
curl -X GET https://us.api.concursolutions.com/travel/v4/trips/{tripID} \
  -H 'Accept: application/json' \
  -H 'Accept-Encoding: string' \
  -H 'Accept: string'

```

```http
GET https://us.api.concursolutions.com/travel/v4/trips/{tripID} HTTP/1.1
Host: us.api.concursolutions.com
Accept: application/json
Accept-Encoding: string
Accept: string

```

```javascript

const headers = {
  'Accept':'application/json',
  'Accept-Encoding':'string',
  'Accept':'string'
};

fetch('https://us.api.concursolutions.com/travel/v4/trips/{tripID}',
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
  'Accept-Encoding' => 'string',
  'Accept' => 'string'
}

result = RestClient.get 'https://us.api.concursolutions.com/travel/v4/trips/{tripID}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Accept-Encoding': 'string',
  'Accept': 'string'
}

r = requests.get('https://us.api.concursolutions.com/travel/v4/trips/{tripID}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'Accept-Encoding' => 'string',
    'Accept' => 'string',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','https://us.api.concursolutions.com/travel/v4/trips/{tripID}', array(
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
URL obj = new URL("https://us.api.concursolutions.com/travel/v4/trips/{tripID}");
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
        "Accept-Encoding": []string{"string"},
        "Accept": []string{"string"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://us.api.concursolutions.com/travel/v4/trips/{tripID}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /trips/{tripID}`

*v4 - Get Trip record*

Gets the trip record

<h3 id="get__trips_{tripid}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|tripID|path|string(uuid)|true|trip id|
|Accept-Encoding|header|string|true|Accepts gzip|
|Accept|header|string|false|Supports application/xml and application/json|

> Example responses

> 200 Response

```json
{
  "BookedByFirstName": "string",
  "BookedByLastName": "string",
  "BookedVia": "string",
  "Bookings": [
    {
      "AgencyName": "string",
      "AgencyPCC": "string",
      "AirfareQuotes": [
        {
          "AirlineCharges": {
            "Fixed": [
              {
                "Amount": 0,
                "Currency": "string",
                "Description": "string",
                "IsPaid": true,
                "IsPrimary": true,
                "SemanticsCode": "string",
                "SemanticsVendorType": "string",
                "StartDateLocal": "string",
                "Vendor": "string",
                "VendorChargeCode": "string"
              }
            ],
            "Percent": [
              {
                "Amount": 0,
                "Currency": "string",
                "Description": "string",
                "IsPaid": true,
                "IsPrimary": true,
                "SemanticsCode": "string",
                "SemanticsVendorType": "string",
                "StartDateLocal": "string",
                "Vendor": "string",
                "VendorChargeCode": "string"
              }
            ],
            "Rate": [
              {
                "Amount": 0,
                "Currency": "string",
                "Description": "string",
                "IsPaid": true,
                "IsPrimary": true,
                "NumUnits": 0,
                "PerUnit": "string",
                "SemanticsCode": "string",
                "SemanticsVendorType": "string",
                "StartDateLocal": "string",
                "Vendor": "string",
                "VendorChargeCode": "string"
              }
            ],
            "RateWithAllowance": [
              {
                "AllowanceAmount": 0,
                "AllowanceIsUnlimited": true,
                "AllowanceNumUnits": 0,
                "AllowanceUnit": "string",
                "Amount": 0,
                "Currency": "string",
                "Description": "string",
                "IsPaid": true,
                "IsPrimary": true,
                "NumUnits": 0,
                "PerUnit": "string",
                "SemanticsCode": "string",
                "SemanticsVendorType": "string",
                "StartDateLocal": "string",
                "Vendor": "string",
                "VendorChargeCode": "string"
              }
            ]
          },
          "BaseFare": 0,
          "BaseFareCurrency": "string",
          "BaseFareNuc": 0,
          "BaseFareNucCurrency": "string",
          "DateCreatedUtc": "string",
          "DateModifiedUtc": "string",
          "Endorsements": "string",
          "IssueByDate": "string",
          "TotalFare": 0,
          "TotalFareCurrency": "string"
        }
      ],
      "AirlineTickets": {
        "AirlineAdjustment": [
          {
            "AddCollectAmount": 0,
            "AdjustmentDateTime": "string",
            "AdjustmentDateTimeUTC": "string",
            "AdjustmentType": "string",
            "AirlineCharges": {
              "Fixed": [
                {
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ],
              "Percent": [
                {
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ],
              "Rate": [
                {
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "NumUnits": 0,
                  "PerUnit": "string",
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ],
              "RateWithAllowance": [
                {
                  "AllowanceAmount": 0,
                  "AllowanceIsUnlimited": true,
                  "AllowanceNumUnits": 0,
                  "AllowanceUnit": "string",
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "NumUnits": 0,
                  "PerUnit": "string",
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ]
            },
            "DateCreatedUtc": "string",
            "DateModifiedUtc": "string",
            "PassengerName": "string",
            "PlatingCarrierNumericCode": "string",
            "PlatingControlNumber": "string",
            "RecordLocator": "string",
            "Taxes": [
              {
                "TaxAmount": 0,
                "TaxAuthority": "string",
                "TaxName": "string",
                "TaxRate": 0,
                "TaxType": "string"
              }
            ],
            "TotalAdjustment": 0,
            "TotalAdjustmentCurrency": "string"
          }
        ],
        "AirlineTicket": [
          {
            "AccountingLine": {
              "AirlineCode": "string",
              "AmountPaid": "string",
              "AmountPaidCurrency": "string",
              "CCNumber": "string",
              "Comment": "string",
              "Commission": "string",
              "CommissionCurrency": "string",
              "ExchangedTicketNumber": "string",
              "FOPMethod": "string",
              "Fare": "string",
              "FareCurrency": "string",
              "IssueDate": "string",
              "MCOType": "string",
              "Tax": "string",
              "TaxCurrency": "string",
              "TranControlNbr": "string",
              "TranPlatingNbr": "string"
            },
            "AddCollectAmount": 0,
            "AirlineCharges": {
              "Fixed": [
                {
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ],
              "Percent": [
                {
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ],
              "Rate": [
                {
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "NumUnits": 0,
                  "PerUnit": "string",
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ],
              "RateWithAllowance": [
                {
                  "AllowanceAmount": 0,
                  "AllowanceIsUnlimited": true,
                  "AllowanceNumUnits": 0,
                  "AllowanceUnit": "string",
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "NumUnits": 0,
                  "PerUnit": "string",
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ]
            },
            "AirlineTicketCoupons": [
              {
                "ClassOfService": "string",
                "CouponNumber": 0,
                "CouponStatus": "string",
                "EndCityCode": "string",
                "FlightNumber": "string",
                "NotValidAfterDate": "string",
                "NotValidBeforeDate": "string",
                "RateCode": "string",
                "StartCityCode": "string",
                "StartDateLocal": "string",
                "Status": "string",
                "TicketDesignator": "string",
                "Vendor": "string"
              }
            ],
            "AirlineTicketExchanges": [
              {
                "Amount": 0,
                "AppliedSegment1": 0,
                "AppliedSegment10": 0,
                "AppliedSegment2": 0,
                "AppliedSegment3": 0,
                "AppliedSegment4": 0,
                "AppliedSegment5": 0,
                "AppliedSegment6": 0,
                "AppliedSegment7": 0,
                "AppliedSegment8": 0,
                "AppliedSegment9": 0,
                "Currency": "string",
                "DateModifiedUtc": "string",
                "OldRecordLocator": "string",
                "PlatingCarrierNumericCode": "string",
                "PlatingControlNumber": "string"
              }
            ],
            "AirlineTicketFareBreakups": [
              {
                "BaseFare": 0,
                "ClassOfService": "string",
                "Currency": "string",
                "EndCityCode": "string",
                "IsRefundable": true,
                "StartCityCode": "string",
                "TotalFare": 0,
                "Vendor": "string"
              }
            ],
            "BaseFare": 0,
            "BaseFareCurrency": "string",
            "BaseFareNuc": 0,
            "BaseFareNucCurrency": "string",
            "ComparisonFare": 0,
            "ComparisonFareCurrency": "string",
            "DateCreatedUtc": "string",
            "DateModifiedUtc": "string",
            "Endorsements": "string",
            "InvoiceNumber": "string",
            "IssueDateTime": "string",
            "IssueDateTimeUTC": "string",
            "IssuingIataAgencyNumber": 0,
            "IssuingPseudoCity": "string",
            "LinearFareConstructor": "string",
            "MasterTicketNumber": "string",
            "NameReference": "string",
            "PassengerName": "string",
            "PlatingCarrierNumericCode": "string",
            "PlatingControlNumber": "string",
            "ProgramCarrierCode": "string",
            "ProgramMembershipNumber": "string",
            "RecordLocator": "string",
            "SabreDkNumber": "string",
            "Taxes": [
              {
                "TaxAmount": 0,
                "TaxAuthority": "string",
                "TaxName": "string",
                "TaxRate": 0,
                "TaxType": "string"
              }
            ],
            "TicketType": "string",
            "Ticketless": true,
            "TotalFare": 0,
            "TotalFareCurrency": "string",
            "TourIdentifier": "string"
          }
        ],
        "ManualAirlineTicket": [
          {
            "AirlineCharges": {
              "Fixed": [
                {
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ],
              "Percent": [
                {
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ],
              "Rate": [
                {
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "NumUnits": 0,
                  "PerUnit": "string",
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ],
              "RateWithAllowance": [
                {
                  "AllowanceAmount": 0,
                  "AllowanceIsUnlimited": true,
                  "AllowanceNumUnits": 0,
                  "AllowanceUnit": "string",
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "NumUnits": 0,
                  "PerUnit": "string",
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ]
            },
            "BaseFare": 0,
            "BaseFareCurrency": "string",
            "DateCreatedUtc": "string",
            "DateModifiedUtc": "string",
            "Taxes": [
              {
                "TaxAmount": 0,
                "TaxAuthority": "string",
                "TaxName": "string",
                "TaxRate": 0,
                "TaxType": "string"
              }
            ],
            "TotalFare": 0,
            "TotalFareCurrency": "string"
          }
        ]
      },
      "BookingOwner": "string",
      "BookingSource": "string",
      "Charges": {
        "Fixed": [
          {
            "Amount": 0,
            "Currency": "string",
            "Description": "string",
            "IsPaid": true,
            "IsPrimary": true,
            "SemanticsCode": "string",
            "SemanticsVendorType": "string",
            "StartDateLocal": "string",
            "Vendor": "string",
            "VendorChargeCode": "string"
          }
        ],
        "Percent": [
          {
            "Amount": 0,
            "Currency": "string",
            "Description": "string",
            "IsPaid": true,
            "IsPrimary": true,
            "SemanticsCode": "string",
            "SemanticsVendorType": "string",
            "StartDateLocal": "string",
            "Vendor": "string",
            "VendorChargeCode": "string"
          }
        ],
        "Rate": [
          {
            "Amount": 0,
            "Currency": "string",
            "Description": "string",
            "IsPaid": true,
            "IsPrimary": true,
            "NumUnits": 0,
            "PerUnit": "string",
            "SemanticsCode": "string",
            "SemanticsVendorType": "string",
            "StartDateLocal": "string",
            "Vendor": "string",
            "VendorChargeCode": "string"
          }
        ],
        "RateWithAllowance": [
          {
            "AllowanceAmount": 0,
            "AllowanceIsUnlimited": true,
            "AllowanceNumUnits": 0,
            "AllowanceUnit": "string",
            "Amount": 0,
            "Currency": "string",
            "Description": "string",
            "IsPaid": true,
            "IsPrimary": true,
            "NumUnits": 0,
            "PerUnit": "string",
            "SemanticsCode": "string",
            "SemanticsVendorType": "string",
            "StartDateLocal": "string",
            "Vendor": "string",
            "VendorChargeCode": "string"
          }
        ]
      },
      "DateBookedLocal": "string",
      "DateCreatedUtc": "string",
      "DateModifiedUtc": "string",
      "Delivery": {
        "AddressLine1": "string",
        "AddressLine2": "string",
        "City": "string",
        "Country": "string",
        "Email": "string",
        "Latitude": 0,
        "LocationAdditionalDetails": "string",
        "LocationDesc": "string",
        "LocationName": "string",
        "Longitude": 0,
        "PhoneNumber": "string",
        "ReferenceNumber": "string",
        "State": "string",
        "Type": "string",
        "Zip": "string"
      },
      "FormOfPaymentName": "string",
      "FormOfPaymentType": "string",
      "IsGhostCard": true,
      "ItinSourceName": "string",
      "LastTicketDateUtc": "string",
      "MiscChargeOrders": [
        {
          "DateCreatedUtc": "string",
          "DateModifiedUtc": "string",
          "IssueDate": "string",
          "PlatingCarrierNumericCode": "string",
          "PlatingControlNumber": "string",
          "TotalAmount": 0,
          "TotalAmountCurrency": "string"
        }
      ],
      "PassPrograms": [
        {
          "Amount": 0,
          "Name": "string",
          "Type": "string",
          "UserFirstName": "string",
          "UserLastName": "string"
        }
      ],
      "Passengers": [
        {
          "City": "string",
          "Country": "string",
          "FirstNameNumber": 0,
          "FrequentTravelerPrograms": {
            "FrequentFlyer": [
              {
                "AirlineVendor": "string",
                "Description": "string",
                "DiscountProgramExpirationDate": "string",
                "DiscountProgramType": "string",
                "FrequentFlyerNumber": "string",
                "Status": "string",
                "StatusExpirationDate": "string"
              }
            ],
            "RailProgram": [
              {
                "Description": "string",
                "DiscountProgramExpirationDate": "string",
                "DiscountProgramType": "string",
                "ProgramNumber": "string",
                "Status": "string",
                "StatusExpirationDate": "string"
              }
            ]
          },
          "LastNameNumber": 0,
          "NameFirst": "string",
          "NameLast": "string",
          "NameMiddle": "string",
          "NamePrefix": "string",
          "NameRemark": "string",
          "NameSuffix": "string",
          "NameTitle": "string",
          "PostalCode": "string",
          "State": "string",
          "StreetAddress": "string",
          "StreetAddress2": "string",
          "TextName": "string"
        }
      ],
      "PhoneNumbers": [
        {
          "Description": "string",
          "PassengerRPH": 0,
          "PhoneNumber": "string",
          "Type": "string"
        }
      ],
      "RailPayments": {
        "RailAdjustment": [
          {
            "AdjustmentDateTime": "string",
            "AdjustmentDateTimeUTC": "string",
            "AdjustmentType": "string",
            "DateCreatedUtc": "string",
            "DateModifiedUtc": "string",
            "RailCharges": {
              "Fixed": [
                {
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ],
              "Percent": [
                {
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ],
              "Rate": [
                {
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "NumUnits": 0,
                  "PerUnit": "string",
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ],
              "RateWithAllowance": [
                {
                  "AllowanceAmount": 0,
                  "AllowanceIsUnlimited": true,
                  "AllowanceNumUnits": 0,
                  "AllowanceUnit": "string",
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "NumUnits": 0,
                  "PerUnit": "string",
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ]
            },
            "Taxes": [
              {
                "TaxAmount": 0,
                "TaxAuthority": "string",
                "TaxName": "string",
                "TaxRate": 0,
                "TaxType": "string"
              }
            ],
            "TicketDocumentIdentifier": "string",
            "TotalAdjustment": 0,
            "TotalAdjustmentCurrency": "string"
          }
        ],
        "RailPayment": [
          {
            "BaseFare": 0,
            "BaseFareCurrency": "string",
            "DateCreatedUtc": "string",
            "DateModifiedUtc": "string",
            "IncludesVAT": true,
            "IssueByDate": "string",
            "IssueDateTime": "string",
            "IssueDateTimeUTC": "string",
            "RailCharges": {
              "Fixed": [
                {
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ],
              "Percent": [
                {
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ],
              "Rate": [
                {
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "NumUnits": 0,
                  "PerUnit": "string",
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ],
              "RateWithAllowance": [
                {
                  "AllowanceAmount": 0,
                  "AllowanceIsUnlimited": true,
                  "AllowanceNumUnits": 0,
                  "AllowanceUnit": "string",
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "NumUnits": 0,
                  "PerUnit": "string",
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ]
            },
            "TaxInvoice": true,
            "Taxes": [
              {
                "TaxAmount": 0,
                "TaxAuthority": "string",
                "TaxName": "string",
                "TaxRate": 0,
                "TaxType": "string"
              }
            ],
            "TicketDocumentIdentifier": "string",
            "TicketType": "string",
            "TotalFare": 0,
            "TotalFareCurrency": "string",
            "vatApplicable": true
          }
        ]
      },
      "RecordLocator": "string",
      "Remarks": {
        "TripLinkRemarks": [
          {
            "TripLinkRemark": [
              {
                "Text": "string"
              }
            ]
          }
        ]
      },
      "Segments": {
        "Air": [
          {
            "AircraftCode": "string",
            "Bags": "string",
            "Cabin": "string",
            "CancellationNumber": "string",
            "CancellationPolicy": "string",
            "CarbonEmissionLbs": 0,
            "CarbonModel": 0,
            "Charges": {
              "Fixed": [
                {
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ],
              "Percent": [
                {
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ],
              "Rate": [
                {
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "NumUnits": 0,
                  "PerUnit": "string",
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ],
              "RateWithAllowance": [
                {
                  "AllowanceAmount": 0,
                  "AllowanceIsUnlimited": true,
                  "AllowanceNumUnits": 0,
                  "AllowanceUnit": "string",
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "NumUnits": 0,
                  "PerUnit": "string",
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ]
            },
            "CheckedBaggage": "string",
            "ClassOfService": "string",
            "ConfirmationNumber": "string",
            "DateCancelledUtc": "string",
            "DateCreatedUtc": "string",
            "DateModifiedUtc": "string",
            "Duration": 0,
            "ETicket": "string",
            "EndCityCode": "string",
            "EndDateLocal": "string",
            "EndDateUtc": "string",
            "EndGate": "string",
            "EndTerminal": "string",
            "FlightNumber": "string",
            "FrequentTravelerId": "string",
            "IsOpenSegment": true,
            "IsPreferredVendor": 0,
            "IsUpgradeAllowed": true,
            "LegId": 0,
            "Meals": "string",
            "Miles": 0,
            "Notes": "string",
            "NumStops": 0,
            "OpenSegment": "string",
            "OperatedByFlightNumber": "string",
            "OperatedByVendor": "string",
            "OperatedByVendorName": "string",
            "Remarks": {
              "TripLinkRemarks": [
                {
                  "TripLinkRemark": [
                    {}
                  ]
                }
              ]
            },
            "RuleViolations": [
              {
                "CompanyReasonCode": "string",
                "CompanyRuleText": "string",
                "ViolationReasonCode": 0
              }
            ],
            "Seats": [
              {
                "PassengerRph": 0,
                "SeatNumber": "string",
                "Status": "string"
              }
            ],
            "Services": "string",
            "SpecialInstructions": "string",
            "StartCityCode": "string",
            "StartDateLocal": "string",
            "StartDateUtc": "string",
            "StartGate": "string",
            "StartTerminal": "string",
            "Status": "string",
            "TimeZone": "string",
            "TimeZoneId": 0,
            "UpgradedDateTime": "string",
            "Vendor": "string",
            "VendorFlags": "string",
            "VendorName": "string"
          }
        ],
        "Car": [
          {
            "AirCondition": "string",
            "Body": "string",
            "CancellationNumber": "string",
            "Charges": {
              "Fixed": [
                {
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ],
              "Percent": [
                {
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ],
              "Rate": [
                {
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "NumUnits": 0,
                  "PerUnit": "string",
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ],
              "RateWithAllowance": [
                {
                  "AllowanceAmount": 0,
                  "AllowanceIsUnlimited": true,
                  "AllowanceNumUnits": 0,
                  "AllowanceUnit": "string",
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "NumUnits": 0,
                  "PerUnit": "string",
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ]
            },
            "Class": "string",
            "ConfirmationNumber": "string",
            "Currency": "string",
            "DailyRate": 0,
            "DateCancelledUtc": "string",
            "DateCreatedUtc": "string",
            "DateModifiedUtc": "string",
            "DiscountCode": "string",
            "DropoffCollectionAddress1": "string",
            "DropoffCollectionAddressType": "string",
            "DropoffCollectionCategory": "string",
            "DropoffCollectionCity": "string",
            "DropoffCollectionCityCode": "string",
            "DropoffCollectionCountry": "string",
            "DropoffCollectionLatitude": "string",
            "DropoffCollectionLongitude": "string",
            "DropoffCollectionNumber": "string",
            "DropoffCollectionPhoneNumber": "string",
            "DropoffCollectionPostalCode": "string",
            "DropoffCollectionState": "string",
            "EndAddress": "string",
            "EndAddress2": "string",
            "EndCity": "string",
            "EndCityCode": "string",
            "EndCloseTime": "string",
            "EndCountry": "string",
            "EndDateLocal": "string",
            "EndDateUtc": "string",
            "EndLatitude": 0,
            "EndLongitude": 0,
            "EndOpenTime": "string",
            "EndPhoneNumber": "string",
            "EndPostalCode": "string",
            "EndState": "string",
            "IsGhostCard": true,
            "IsPreferredVendor": 0,
            "IsUpgradeAllowed": true,
            "Notes": "string",
            "NumCars": 0,
            "NumPersons": 0,
            "PhoneNumber": "string",
            "PickupDeliveryAddress1": "string",
            "PickupDeliveryAddressType": "string",
            "PickupDeliveryCategory": "string",
            "PickupDeliveryCity": "string",
            "PickupDeliveryCityCode": "string",
            "PickupDeliveryCountry": "string",
            "PickupDeliveryLatitude": "string",
            "PickupDeliveryLongitude": "string",
            "PickupDeliveryNumber": "string",
            "PickupDeliveryPhoneNumber": "string",
            "PickupDeliveryPostalCode": "string",
            "PickupDeliveryState": "string",
            "RateCode": "string",
            "RateType": "string",
            "Remarks": {
              "TripLinkRemarks": [
                {
                  "TripLinkRemark": [
                    {}
                  ]
                }
              ]
            },
            "SpecialEquipment": "string",
            "SpecialInstructions": "string",
            "StartAddress": "string",
            "StartAddress2": "string",
            "StartCity": "string",
            "StartCityCode": "string",
            "StartCloseTime": "string",
            "StartCountry": "string",
            "StartDateLocal": "string",
            "StartDateUtc": "string",
            "StartLatitude": 0,
            "StartLocation": "string",
            "StartLongitude": 0,
            "StartOpenTime": "string",
            "StartPostalCode": "string",
            "StartState": "string",
            "Status": "string",
            "TimeZone": "string",
            "TimeZoneId": 0,
            "TotalRate": 0,
            "Transmission": "string",
            "UpgradedDateTime": "string",
            "Vendor": "string",
            "VendorFlags": "string",
            "VendorName": "string"
          }
        ],
        "Dining": [
          {
            "CancellationNumber": "string",
            "Charges": {
              "Fixed": [
                {
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ],
              "Percent": [
                {
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ],
              "Rate": [
                {
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "NumUnits": 0,
                  "PerUnit": "string",
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ],
              "RateWithAllowance": [
                {
                  "AllowanceAmount": 0,
                  "AllowanceIsUnlimited": true,
                  "AllowanceNumUnits": 0,
                  "AllowanceUnit": "string",
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "NumUnits": 0,
                  "PerUnit": "string",
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ]
            },
            "ConfirmationNumber": "string",
            "DateCancelledUtc": "string",
            "DateCreatedUtc": "string",
            "DateModifiedUtc": "string",
            "EndDateLocal": "string",
            "EndDateUtc": "string",
            "FrequentTravelerId": "string",
            "IsPreferredVendor": 0,
            "IsUpgradeAllowed": true,
            "Name": "string",
            "Notes": "string",
            "NumPersons": 0,
            "PhoneNumber": "string",
            "Remarks": {
              "TripLinkRemarks": [
                {
                  "TripLinkRemark": [
                    {}
                  ]
                }
              ]
            },
            "ReservationId": "string",
            "StartAddress": "string",
            "StartAddress2": "string",
            "StartCity": "string",
            "StartCountry": "string",
            "StartDateLocal": "string",
            "StartDateUtc": "string",
            "StartLatitude": 0,
            "StartLongitude": 0,
            "StartPostalCode": "string",
            "StartState": "string",
            "Status": "string",
            "TimeZone": "string",
            "TimeZoneId": 0,
            "UpgradedDateTime": "string",
            "Vendor": "string",
            "VendorFlags": "string",
            "VendorName": "string"
          }
        ],
        "Hotel": [
          {
            "Breakfast": true,
            "CancellationNumber": "string",
            "CancellationPolicy": "string",
            "Charges": {
              "Fixed": [
                {
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ],
              "Percent": [
                {
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ],
              "Rate": [
                {
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "NumUnits": 0,
                  "PerUnit": "string",
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ],
              "RateWithAllowance": [
                {
                  "AllowanceAmount": 0,
                  "AllowanceIsUnlimited": true,
                  "AllowanceNumUnits": 0,
                  "AllowanceUnit": "string",
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "NumUnits": 0,
                  "PerUnit": "string",
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ]
            },
            "CheckinTime": "string",
            "CheckoutTime": "string",
            "ConfirmationNumber": "string",
            "Currency": "string",
            "DailyRate": 0,
            "DateCancelledUtc": "string",
            "DateCreatedUtc": "string",
            "DateModifiedUtc": "string",
            "DirectBill": true,
            "DiscountCode": "string",
            "Email": "string",
            "EndDateLocal": "string",
            "EndDateUtc": "string",
            "EquipmentCode": "string",
            "FaxNumber": "string",
            "FrequentTravelerId": "string",
            "HotelPropertyId": "string",
            "IncludedCustomAmenities": "string",
            "IsGhostCard": true,
            "IsPreferredVendor": 0,
            "IsUpgradeAllowed": true,
            "ModificationCode": "string",
            "Name": "string",
            "Notes": "string",
            "NumPersons": 0,
            "NumRooms": 0,
            "Parking": true,
            "PartnerMembershipId": "string",
            "PassiveType": "string",
            "PhoneNumber": "string",
            "RateAccess": "string",
            "RateCode": "string",
            "RateType": "string",
            "Remarks": {
              "TripLinkRemarks": [
                {
                  "TripLinkRemark": [
                    {}
                  ]
                }
              ]
            },
            "RoomDescription": "string",
            "RoomType": "string",
            "SpecialInstructions": "string",
            "StartAddress": "string",
            "StartAddress2": "string",
            "StartCity": "string",
            "StartCityCode": "string",
            "StartCountry": "string",
            "StartDateLocal": "string",
            "StartDateUtc": "string",
            "StartLatitude": 0,
            "StartLongitude": 0,
            "StartPostalCode": "string",
            "StartState": "string",
            "Status": "string",
            "TimeZone": "string",
            "TimeZoneId": 0,
            "TotalRate": 0,
            "UpgradedDateTime": "string",
            "Vendor": "string",
            "VendorFlags": "string",
            "VendorName": "string",
            "Wifi": true
          }
        ],
        "Parking": [
          {
            "CancellationNumber": "string",
            "Charges": {
              "Fixed": [
                {
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ],
              "Percent": [
                {
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ],
              "Rate": [
                {
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "NumUnits": 0,
                  "PerUnit": "string",
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ],
              "RateWithAllowance": [
                {
                  "AllowanceAmount": 0,
                  "AllowanceIsUnlimited": true,
                  "AllowanceNumUnits": 0,
                  "AllowanceUnit": "string",
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "NumUnits": 0,
                  "PerUnit": "string",
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ]
            },
            "ClassOfService": "string",
            "ConfirmationNumber": "string",
            "Currency": "string",
            "DateCancelledUtc": "string",
            "DateCreatedUtc": "string",
            "DateModifiedUtc": "string",
            "EndDateLocal": "string",
            "EndDateUtc": "string",
            "FrequentTravelerId": "string",
            "IsPreferredVendor": 0,
            "IsUpgradeAllowed": true,
            "Name": "string",
            "Notes": "string",
            "OperatedByVendor": "string",
            "ParkingLocationId": "string",
            "PhoneNumber": "string",
            "Pin": "string",
            "RateCode": "string",
            "Remarks": {
              "TripLinkRemarks": [
                {
                  "TripLinkRemark": [
                    {}
                  ]
                }
              ]
            },
            "StartAddress": "string",
            "StartAddress2": "string",
            "StartCity": "string",
            "StartCityCode": "string",
            "StartCountry": "string",
            "StartDateLocal": "string",
            "StartDateUtc": "string",
            "StartLocation": "string",
            "StartPostalCode": "string",
            "StartState": "string",
            "Status": "string",
            "TimeZone": "string",
            "TimeZoneId": 0,
            "TotalRate": 0,
            "UpgradedDateTime": "string",
            "Vendor": "string",
            "VendorFlags": "string",
            "VendorName": "string"
          }
        ],
        "Rail": [
          {
            "Amenities": "string",
            "Cabin": "string",
            "CancellationNumber": "string",
            "CarbonEmissionLbs": 0,
            "CarbonModel": 0,
            "Charges": {
              "Fixed": [
                {
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ],
              "Percent": [
                {
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ],
              "Rate": [
                {
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "NumUnits": 0,
                  "PerUnit": "string",
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ],
              "RateWithAllowance": [
                {
                  "AllowanceAmount": 0,
                  "AllowanceIsUnlimited": true,
                  "AllowanceNumUnits": 0,
                  "AllowanceUnit": "string",
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "NumUnits": 0,
                  "PerUnit": "string",
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ]
            },
            "ClassOfService": "string",
            "ConfirmationNumber": "string",
            "Currency": "string",
            "DateCancelledUtc": "string",
            "DateCreatedUtc": "string",
            "DateModifiedUtc": "string",
            "DiscountCode": "string",
            "Duration": 0,
            "ETicket": "string",
            "EndCity": "string",
            "EndCityCode": "string",
            "EndCountry": "string",
            "EndDateLocal": "string",
            "EndDateUtc": "string",
            "EndLatitude": 0,
            "EndLongitude": 0,
            "EndPlatform": "string",
            "EndRailStation": "string",
            "EndRailStationName": "string",
            "EndState": "string",
            "FrequentTravelerId": "string",
            "IsPreferredVendor": 0,
            "IsUpgradeAllowed": true,
            "LegId": 0,
            "Meals": "string",
            "Miles": 0,
            "Notes": "string",
            "NumPersons": 0,
            "NumStops": 0,
            "OperatedByTrainNumber": "string",
            "OperatedByVendor": "string",
            "RateCode": "string",
            "Remarks": {
              "TripLinkRemarks": [
                {
                  "TripLinkRemark": [
                    {}
                  ]
                }
              ]
            },
            "RouteRestrictCode": "string",
            "Seats": [
              {
                "Amenities": "string",
                "BerthPosition": "string",
                "Deck": "string",
                "FacingForward": "string",
                "FareSpaceComfort": "string",
                "PassengerRph": 0,
                "SeatNumber": "string",
                "SeatPosition": "string",
                "SeatType": "string",
                "SpaceType": "string",
                "Status": "string",
                "WagonNumber": "string",
                "WagonType": "string"
              }
            ],
            "SpecialInstructions": "string",
            "StartCity": "string",
            "StartCityCode": "string",
            "StartCountry": "string",
            "StartDateLocal": "string",
            "StartDateUtc": "string",
            "StartLatitude": 0,
            "StartLongitude": 0,
            "StartPlatform": "string",
            "StartRailStation": "string",
            "StartRailStationName": "string",
            "StartState": "string",
            "Status": "string",
            "TimeZone": "string",
            "TimeZoneId": 0,
            "TotalRate": 0,
            "TrainNumber": "string",
            "TrainTypeCode": "string",
            "TrainTypeName": "string",
            "TransportMode": "string",
            "UpgradedDateTime": "string",
            "Vendor": "string",
            "VendorFlags": "string",
            "VendorName": "string",
            "WagonNumber": "string"
          }
        ],
        "Ride": [
          {
            "CancellationNumber": "string",
            "CancellationPolicy": "string",
            "Charges": {
              "Fixed": [
                {
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ],
              "Percent": [
                {
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ],
              "Rate": [
                {
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "NumUnits": 0,
                  "PerUnit": "string",
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ],
              "RateWithAllowance": [
                {
                  "AllowanceAmount": 0,
                  "AllowanceIsUnlimited": true,
                  "AllowanceNumUnits": 0,
                  "AllowanceUnit": "string",
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "NumUnits": 0,
                  "PerUnit": "string",
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ]
            },
            "ConfirmationNumber": "string",
            "Currency": "string",
            "DateCancelledUtc": "string",
            "DateCreatedUtc": "string",
            "DateModifiedUtc": "string",
            "DropoffInstructions": "string",
            "Duration": 0,
            "EndAddress": "string",
            "EndAddress2": "string",
            "EndCity": "string",
            "EndCityCode": "string",
            "EndCountry": "string",
            "EndDateLocal": "string",
            "EndDateUtc": "string",
            "EndLatitude": 0,
            "EndLocationCode": "string",
            "EndLongitude": 0,
            "EndPostalCode": "string",
            "EndState": "string",
            "IsGhostCard": true,
            "IsPreferredVendor": 0,
            "IsUpgradeAllowed": true,
            "MeetingInstructions": "string",
            "Miles": 0,
            "Name": "string",
            "Notes": "string",
            "NumPersons": 0,
            "NumberOfHours": 0,
            "OperatedByVendorName": "string",
            "PassiveCityCode": "string",
            "PhoneNumber": "string",
            "PickupInstructions": "string",
            "ProviderFeedback": "string",
            "Rate": 0,
            "RateDescription": "string",
            "RateNotes": "string",
            "RateType": "string",
            "Remarks": {
              "TripLinkRemarks": [
                {
                  "TripLinkRemark": [
                    {}
                  ]
                }
              ]
            },
            "ReservationId": "string",
            "SpecialInstructions": "string",
            "StartAddress": "string",
            "StartAddress2": "string",
            "StartCity": "string",
            "StartCityCode": "string",
            "StartCountry": "string",
            "StartDateLocal": "string",
            "StartDateUtc": "string",
            "StartLatitude": 0,
            "StartLocation": "string",
            "StartLocationCode": "string",
            "StartLocationName": "string",
            "StartLongitude": 0,
            "StartPostalCode": "string",
            "StartState": "string",
            "TimeZone": "string",
            "TimeZoneId": 0,
            "TotalRate": 0,
            "UpgradedDateTime": "string",
            "Vendor": "string",
            "VendorFlags": "string",
            "VendorName": "string"
          }
        ],
        "Travel": [
          {
            "CancellationNumber": "string",
            "Charges": {
              "Fixed": [
                {
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ],
              "Percent": [
                {
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ],
              "Rate": [
                {
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "NumUnits": 0,
                  "PerUnit": "string",
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ],
              "RateWithAllowance": [
                {
                  "AllowanceAmount": 0,
                  "AllowanceIsUnlimited": true,
                  "AllowanceNumUnits": 0,
                  "AllowanceUnit": "string",
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "NumUnits": 0,
                  "PerUnit": "string",
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ]
            },
            "ConfirmationNumber": "string",
            "Currency": "string",
            "DailyRate": 0,
            "DateCancelledUtc": "string",
            "DateCreatedUtc": "string",
            "DateModifiedUtc": "string",
            "EndAddress": "string",
            "EndAddress2": "string",
            "EndCity": "string",
            "EndCityCode": "string",
            "EndCountry": "string",
            "EndDateLocal": "string",
            "EndDateUtc": "string",
            "EndLatitude": 0,
            "EndLocation": "string",
            "EndLongitude": 0,
            "EndPostalCode": "string",
            "EndState": "string",
            "IsGhostCard": true,
            "Notes": "string",
            "NumPersons": 0,
            "PhoneNumber": "string",
            "Remarks": {
              "TripLinkRemarks": [
                {
                  "TripLinkRemark": [
                    {}
                  ]
                }
              ]
            },
            "SpecialInstructions": "string",
            "StartAddress": "string",
            "StartAddress2": "string",
            "StartCity": "string",
            "StartCityCode": "string",
            "StartCountry": "string",
            "StartDateLocal": "string",
            "StartDateUtc": "string",
            "StartLatitude": 0,
            "StartLocation": "string",
            "StartLongitude": 0,
            "StartPostalCode": "string",
            "StartState": "string",
            "Status": "string",
            "TimeZone": "string",
            "TimeZoneId": 0,
            "TotalRate": 0,
            "TransportMode": "string",
            "Vendor": "string",
            "VendorName": "string"
          }
        ]
      },
      "TicketMailingAddress": "string",
      "TicketPickupLocation": "string",
      "TicketPickupNumber": "string",
      "WaitListSegments": {
        "SegmentOption": [
          {
            "Flight": [
              {
                "ArrAirp": "string",
                "Cabin": "string",
                "Carrier": "string",
                "DepAirp": "string",
                "FlightNum": "string"
              }
            ],
            "SegmentIndex": "string",
            "StatusCode": "string",
            "TimeStamp": "string"
          }
        ]
      },
      "Warnings": [
        {
          "Code": [
            "string"
          ],
          "Text": [
            "string"
          ],
          "Type": [
            "string"
          ]
        }
      ],
      "WebAddresses": [
        {
          "Description": "string",
          "Format": "string",
          "PassengerRPH": 0,
          "Type": "string",
          "WebAddress": "string"
        }
      ]
    }
  ],
  "CancelComments": "string",
  "ClientLocator": "string",
  "Comments": "string",
  "CustomAttributes": [
    {
      "Data": "string",
      "DataType": "string",
      "DisplayOnItinerary": true,
      "DisplayTitle": "string",
      "ExternalId": 0,
      "Name": "string"
    }
  ],
  "DateBookedLocal": "string",
  "DateCreatedUtc": "string",
  "DateModifiedUtc": "string",
  "Description": "string",
  "EndDateLocal": "string",
  "EndDateUtc": "string",
  "HasOpenBookingPassive": true,
  "IsPersonal": true,
  "ItinLocator": "string",
  "ProjectName": "string",
  "StartDateLocal": "string",
  "StartDateUtc": "string",
  "TravelRequestId": "string",
  "TripLinkLocator": "string",
  "TripName": "string",
  "TripStatus": 0,
  "UserLoginId": "string",
  "id": "string"
}
```

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<Itinerary>
  <BookedByFirstName>string</BookedByFirstName>
  <BookedByLastName>string</BookedByLastName>
  <BookedVia>string</BookedVia>
  <Bookings>
    <AgencyName>string</AgencyName>
    <AgencyPCC>string</AgencyPCC>
    <AirfareQuotes>
      <AirlineCharges>
        <Fixed>
          <Amount>0</Amount>
          <Currency>string</Currency>
          <Description>string</Description>
          <IsPaid>true</IsPaid>
          <IsPrimary>true</IsPrimary>
          <SemanticsCode>string</SemanticsCode>
          <SemanticsVendorType>string</SemanticsVendorType>
          <StartDateLocal>string</StartDateLocal>
          <Vendor>string</Vendor>
          <VendorChargeCode>string</VendorChargeCode>
        </Fixed>
        <Percent>
          <Amount>0</Amount>
          <Currency>string</Currency>
          <Description>string</Description>
          <IsPaid>true</IsPaid>
          <IsPrimary>true</IsPrimary>
          <SemanticsCode>string</SemanticsCode>
          <SemanticsVendorType>string</SemanticsVendorType>
          <StartDateLocal>string</StartDateLocal>
          <Vendor>string</Vendor>
          <VendorChargeCode>string</VendorChargeCode>
        </Percent>
        <Rate>
          <Amount>0</Amount>
          <Currency>string</Currency>
          <Description>string</Description>
          <IsPaid>true</IsPaid>
          <IsPrimary>true</IsPrimary>
          <NumUnits>0</NumUnits>
          <PerUnit>string</PerUnit>
          <SemanticsCode>string</SemanticsCode>
          <SemanticsVendorType>string</SemanticsVendorType>
          <StartDateLocal>string</StartDateLocal>
          <Vendor>string</Vendor>
          <VendorChargeCode>string</VendorChargeCode>
        </Rate>
        <RateWithAllowance>
          <AllowanceAmount>0</AllowanceAmount>
          <AllowanceIsUnlimited>true</AllowanceIsUnlimited>
          <AllowanceNumUnits>0</AllowanceNumUnits>
          <AllowanceUnit>string</AllowanceUnit>
          <Amount>0</Amount>
          <Currency>string</Currency>
          <Description>string</Description>
          <IsPaid>true</IsPaid>
          <IsPrimary>true</IsPrimary>
          <NumUnits>0</NumUnits>
          <PerUnit>string</PerUnit>
          <SemanticsCode>string</SemanticsCode>
          <SemanticsVendorType>string</SemanticsVendorType>
          <StartDateLocal>string</StartDateLocal>
          <Vendor>string</Vendor>
          <VendorChargeCode>string</VendorChargeCode>
        </RateWithAllowance>
      </AirlineCharges>
      <BaseFare>0</BaseFare>
      <BaseFareCurrency>string</BaseFareCurrency>
      <BaseFareNuc>0</BaseFareNuc>
      <BaseFareNucCurrency>string</BaseFareNucCurrency>
      <DateCreatedUtc>string</DateCreatedUtc>
      <DateModifiedUtc>string</DateModifiedUtc>
      <Endorsements>string</Endorsements>
      <IssueByDate>string</IssueByDate>
      <TotalFare>0</TotalFare>
      <TotalFareCurrency>string</TotalFareCurrency>
    </AirfareQuotes>
    <AirlineTickets>
      <AirlineAdjustment>
        <AddCollectAmount>0</AddCollectAmount>
        <AdjustmentDateTime>string</AdjustmentDateTime>
        <AdjustmentDateTimeUTC>string</AdjustmentDateTimeUTC>
        <AdjustmentType>string</AdjustmentType>
        <AirlineCharges>
          <Fixed>
            <Amount>0</Amount>
            <Currency>string</Currency>
            <Description>string</Description>
            <IsPaid>true</IsPaid>
            <IsPrimary>true</IsPrimary>
            <SemanticsCode>string</SemanticsCode>
            <SemanticsVendorType>string</SemanticsVendorType>
            <StartDateLocal>string</StartDateLocal>
            <Vendor>string</Vendor>
            <VendorChargeCode>string</VendorChargeCode>
          </Fixed>
          <Percent>
            <Amount>0</Amount>
            <Currency>string</Currency>
            <Description>string</Description>
            <IsPaid>true</IsPaid>
            <IsPrimary>true</IsPrimary>
            <SemanticsCode>string</SemanticsCode>
            <SemanticsVendorType>string</SemanticsVendorType>
            <StartDateLocal>string</StartDateLocal>
            <Vendor>string</Vendor>
            <VendorChargeCode>string</VendorChargeCode>
          </Percent>
          <Rate>
            <Amount>0</Amount>
            <Currency>string</Currency>
            <Description>string</Description>
            <IsPaid>true</IsPaid>
            <IsPrimary>true</IsPrimary>
            <NumUnits>0</NumUnits>
            <PerUnit>string</PerUnit>
            <SemanticsCode>string</SemanticsCode>
            <SemanticsVendorType>string</SemanticsVendorType>
            <StartDateLocal>string</StartDateLocal>
            <Vendor>string</Vendor>
            <VendorChargeCode>string</VendorChargeCode>
          </Rate>
          <RateWithAllowance>
            <AllowanceAmount>0</AllowanceAmount>
            <AllowanceIsUnlimited>true</AllowanceIsUnlimited>
            <AllowanceNumUnits>0</AllowanceNumUnits>
            <AllowanceUnit>string</AllowanceUnit>
            <Amount>0</Amount>
            <Currency>string</Currency>
            <Description>string</Description>
            <IsPaid>true</IsPaid>
            <IsPrimary>true</IsPrimary>
            <NumUnits>0</NumUnits>
            <PerUnit>string</PerUnit>
            <SemanticsCode>string</SemanticsCode>
            <SemanticsVendorType>string</SemanticsVendorType>
            <StartDateLocal>string</StartDateLocal>
            <Vendor>string</Vendor>
            <VendorChargeCode>string</VendorChargeCode>
          </RateWithAllowance>
        </AirlineCharges>
        <DateCreatedUtc>string</DateCreatedUtc>
        <DateModifiedUtc>string</DateModifiedUtc>
        <PassengerName>string</PassengerName>
        <PlatingCarrierNumericCode>string</PlatingCarrierNumericCode>
        <PlatingControlNumber>string</PlatingControlNumber>
        <RecordLocator>string</RecordLocator>
        <Taxes>
          <TaxAmount>0</TaxAmount>
          <TaxAuthority>string</TaxAuthority>
          <TaxName>string</TaxName>
          <TaxRate>0</TaxRate>
          <TaxType>string</TaxType>
        </Taxes>
        <TotalAdjustment>0</TotalAdjustment>
        <TotalAdjustmentCurrency>string</TotalAdjustmentCurrency>
      </AirlineAdjustment>
      <AirlineTicket>
        <AccountingLine>
          <AirlineCode>string</AirlineCode>
          <AmountPaid>string</AmountPaid>
          <AmountPaidCurrency>string</AmountPaidCurrency>
          <CCNumber>string</CCNumber>
          <Comment>string</Comment>
          <Commission>string</Commission>
          <CommissionCurrency>string</CommissionCurrency>
          <ExchangedTicketNumber>string</ExchangedTicketNumber>
          <FOPMethod>string</FOPMethod>
          <Fare>string</Fare>
          <FareCurrency>string</FareCurrency>
          <IssueDate>string</IssueDate>
          <MCOType>string</MCOType>
          <Tax>string</Tax>
          <TaxCurrency>string</TaxCurrency>
          <TranControlNbr>string</TranControlNbr>
          <TranPlatingNbr>string</TranPlatingNbr>
        </AccountingLine>
        <AddCollectAmount>0</AddCollectAmount>
        <AirlineCharges>
          <Fixed>
            <Amount>0</Amount>
            <Currency>string</Currency>
            <Description>string</Description>
            <IsPaid>true</IsPaid>
            <IsPrimary>true</IsPrimary>
            <SemanticsCode>string</SemanticsCode>
            <SemanticsVendorType>string</SemanticsVendorType>
            <StartDateLocal>string</StartDateLocal>
            <Vendor>string</Vendor>
            <VendorChargeCode>string</VendorChargeCode>
          </Fixed>
          <Percent>
            <Amount>0</Amount>
            <Currency>string</Currency>
            <Description>string</Description>
            <IsPaid>true</IsPaid>
            <IsPrimary>true</IsPrimary>
            <SemanticsCode>string</SemanticsCode>
            <SemanticsVendorType>string</SemanticsVendorType>
            <StartDateLocal>string</StartDateLocal>
            <Vendor>string</Vendor>
            <VendorChargeCode>string</VendorChargeCode>
          </Percent>
          <Rate>
            <Amount>0</Amount>
            <Currency>string</Currency>
            <Description>string</Description>
            <IsPaid>true</IsPaid>
            <IsPrimary>true</IsPrimary>
            <NumUnits>0</NumUnits>
            <PerUnit>string</PerUnit>
            <SemanticsCode>string</SemanticsCode>
            <SemanticsVendorType>string</SemanticsVendorType>
            <StartDateLocal>string</StartDateLocal>
            <Vendor>string</Vendor>
            <VendorChargeCode>string</VendorChargeCode>
          </Rate>
          <RateWithAllowance>
            <AllowanceAmount>0</AllowanceAmount>
            <AllowanceIsUnlimited>true</AllowanceIsUnlimited>
            <AllowanceNumUnits>0</AllowanceNumUnits>
            <AllowanceUnit>string</AllowanceUnit>
            <Amount>0</Amount>
            <Currency>string</Currency>
            <Description>string</Description>
            <IsPaid>true</IsPaid>
            <IsPrimary>true</IsPrimary>
            <NumUnits>0</NumUnits>
            <PerUnit>string</PerUnit>
            <SemanticsCode>string</SemanticsCode>
            <SemanticsVendorType>string</SemanticsVendorType>
            <StartDateLocal>string</StartDateLocal>
            <Vendor>string</Vendor>
            <VendorChargeCode>string</VendorChargeCode>
          </RateWithAllowance>
        </AirlineCharges>
        <AirlineTicketCoupons>
          <ClassOfService>string</ClassOfService>
          <CouponNumber>0</CouponNumber>
          <CouponStatus>string</CouponStatus>
          <EndCityCode>string</EndCityCode>
          <FlightNumber>string</FlightNumber>
          <NotValidAfterDate>string</NotValidAfterDate>
          <NotValidBeforeDate>string</NotValidBeforeDate>
          <RateCode>string</RateCode>
          <StartCityCode>string</StartCityCode>
          <StartDateLocal>string</StartDateLocal>
          <Status>string</Status>
          <TicketDesignator>string</TicketDesignator>
          <Vendor>string</Vendor>
        </AirlineTicketCoupons>
        <AirlineTicketExchanges>
          <Amount>0</Amount>
          <AppliedSegment1>0</AppliedSegment1>
          <AppliedSegment10>0</AppliedSegment10>
          <AppliedSegment2>0</AppliedSegment2>
          <AppliedSegment3>0</AppliedSegment3>
          <AppliedSegment4>0</AppliedSegment4>
          <AppliedSegment5>0</AppliedSegment5>
          <AppliedSegment6>0</AppliedSegment6>
          <AppliedSegment7>0</AppliedSegment7>
          <AppliedSegment8>0</AppliedSegment8>
          <AppliedSegment9>0</AppliedSegment9>
          <Currency>string</Currency>
          <DateModifiedUtc>string</DateModifiedUtc>
          <OldRecordLocator>string</OldRecordLocator>
          <PlatingCarrierNumericCode>string</PlatingCarrierNumericCode>
          <PlatingControlNumber>string</PlatingControlNumber>
        </AirlineTicketExchanges>
        <AirlineTicketFareBreakups>
          <BaseFare>0</BaseFare>
          <ClassOfService>string</ClassOfService>
          <Currency>string</Currency>
          <EndCityCode>string</EndCityCode>
          <IsRefundable>true</IsRefundable>
          <StartCityCode>string</StartCityCode>
          <TotalFare>0</TotalFare>
          <Vendor>string</Vendor>
        </AirlineTicketFareBreakups>
        <BaseFare>0</BaseFare>
        <BaseFareCurrency>string</BaseFareCurrency>
        <BaseFareNuc>0</BaseFareNuc>
        <BaseFareNucCurrency>string</BaseFareNucCurrency>
        <ComparisonFare>0</ComparisonFare>
        <ComparisonFareCurrency>string</ComparisonFareCurrency>
        <DateCreatedUtc>string</DateCreatedUtc>
        <DateModifiedUtc>string</DateModifiedUtc>
        <Endorsements>string</Endorsements>
        <InvoiceNumber>string</InvoiceNumber>
        <IssueDateTime>string</IssueDateTime>
        <IssueDateTimeUTC>string</IssueDateTimeUTC>
        <IssuingIataAgencyNumber>0</IssuingIataAgencyNumber>
        <IssuingPseudoCity>string</IssuingPseudoCity>
        <LinearFareConstructor>string</LinearFareConstructor>
        <MasterTicketNumber>string</MasterTicketNumber>
        <NameReference>string</NameReference>
        <PassengerName>string</PassengerName>
        <PlatingCarrierNumericCode>string</PlatingCarrierNumericCode>
        <PlatingControlNumber>string</PlatingControlNumber>
        <ProgramCarrierCode>string</ProgramCarrierCode>
        <ProgramMembershipNumber>string</ProgramMembershipNumber>
        <RecordLocator>string</RecordLocator>
        <SabreDkNumber>string</SabreDkNumber>
        <Taxes>
          <TaxAmount>0</TaxAmount>
          <TaxAuthority>string</TaxAuthority>
          <TaxName>string</TaxName>
          <TaxRate>0</TaxRate>
          <TaxType>string</TaxType>
        </Taxes>
        <TicketType>string</TicketType>
        <Ticketless>true</Ticketless>
        <TotalFare>0</TotalFare>
        <TotalFareCurrency>string</TotalFareCurrency>
        <TourIdentifier>string</TourIdentifier>
      </AirlineTicket>
      <ManualAirlineTicket>
        <AirlineCharges>
          <Fixed>
            <Amount>0</Amount>
            <Currency>string</Currency>
            <Description>string</Description>
            <IsPaid>true</IsPaid>
            <IsPrimary>true</IsPrimary>
            <SemanticsCode>string</SemanticsCode>
            <SemanticsVendorType>string</SemanticsVendorType>
            <StartDateLocal>string</StartDateLocal>
            <Vendor>string</Vendor>
            <VendorChargeCode>string</VendorChargeCode>
          </Fixed>
          <Percent>
            <Amount>0</Amount>
            <Currency>string</Currency>
            <Description>string</Description>
            <IsPaid>true</IsPaid>
            <IsPrimary>true</IsPrimary>
            <SemanticsCode>string</SemanticsCode>
            <SemanticsVendorType>string</SemanticsVendorType>
            <StartDateLocal>string</StartDateLocal>
            <Vendor>string</Vendor>
            <VendorChargeCode>string</VendorChargeCode>
          </Percent>
          <Rate>
            <Amount>0</Amount>
            <Currency>string</Currency>
            <Description>string</Description>
            <IsPaid>true</IsPaid>
            <IsPrimary>true</IsPrimary>
            <NumUnits>0</NumUnits>
            <PerUnit>string</PerUnit>
            <SemanticsCode>string</SemanticsCode>
            <SemanticsVendorType>string</SemanticsVendorType>
            <StartDateLocal>string</StartDateLocal>
            <Vendor>string</Vendor>
            <VendorChargeCode>string</VendorChargeCode>
          </Rate>
          <RateWithAllowance>
            <AllowanceAmount>0</AllowanceAmount>
            <AllowanceIsUnlimited>true</AllowanceIsUnlimited>
            <AllowanceNumUnits>0</AllowanceNumUnits>
            <AllowanceUnit>string</AllowanceUnit>
            <Amount>0</Amount>
            <Currency>string</Currency>
            <Description>string</Description>
            <IsPaid>true</IsPaid>
            <IsPrimary>true</IsPrimary>
            <NumUnits>0</NumUnits>
            <PerUnit>string</PerUnit>
            <SemanticsCode>string</SemanticsCode>
            <SemanticsVendorType>string</SemanticsVendorType>
            <StartDateLocal>string</StartDateLocal>
            <Vendor>string</Vendor>
            <VendorChargeCode>string</VendorChargeCode>
          </RateWithAllowance>
        </AirlineCharges>
        <BaseFare>0</BaseFare>
        <BaseFareCurrency>string</BaseFareCurrency>
        <DateCreatedUtc>string</DateCreatedUtc>
        <DateModifiedUtc>string</DateModifiedUtc>
        <Taxes>
          <TaxAmount>0</TaxAmount>
          <TaxAuthority>string</TaxAuthority>
          <TaxName>string</TaxName>
          <TaxRate>0</TaxRate>
          <TaxType>string</TaxType>
        </Taxes>
        <TotalFare>0</TotalFare>
        <TotalFareCurrency>string</TotalFareCurrency>
      </ManualAirlineTicket>
    </AirlineTickets>
    <BookingOwner>string</BookingOwner>
    <BookingSource>string</BookingSource>
    <Charges>
      <Fixed>
        <Amount>0</Amount>
        <Currency>string</Currency>
        <Description>string</Description>
        <IsPaid>true</IsPaid>
        <IsPrimary>true</IsPrimary>
        <SemanticsCode>string</SemanticsCode>
        <SemanticsVendorType>string</SemanticsVendorType>
        <StartDateLocal>string</StartDateLocal>
        <Vendor>string</Vendor>
        <VendorChargeCode>string</VendorChargeCode>
      </Fixed>
      <Percent>
        <Amount>0</Amount>
        <Currency>string</Currency>
        <Description>string</Description>
        <IsPaid>true</IsPaid>
        <IsPrimary>true</IsPrimary>
        <SemanticsCode>string</SemanticsCode>
        <SemanticsVendorType>string</SemanticsVendorType>
        <StartDateLocal>string</StartDateLocal>
        <Vendor>string</Vendor>
        <VendorChargeCode>string</VendorChargeCode>
      </Percent>
      <Rate>
        <Amount>0</Amount>
        <Currency>string</Currency>
        <Description>string</Description>
        <IsPaid>true</IsPaid>
        <IsPrimary>true</IsPrimary>
        <NumUnits>0</NumUnits>
        <PerUnit>string</PerUnit>
        <SemanticsCode>string</SemanticsCode>
        <SemanticsVendorType>string</SemanticsVendorType>
        <StartDateLocal>string</StartDateLocal>
        <Vendor>string</Vendor>
        <VendorChargeCode>string</VendorChargeCode>
      </Rate>
      <RateWithAllowance>
        <AllowanceAmount>0</AllowanceAmount>
        <AllowanceIsUnlimited>true</AllowanceIsUnlimited>
        <AllowanceNumUnits>0</AllowanceNumUnits>
        <AllowanceUnit>string</AllowanceUnit>
        <Amount>0</Amount>
        <Currency>string</Currency>
        <Description>string</Description>
        <IsPaid>true</IsPaid>
        <IsPrimary>true</IsPrimary>
        <NumUnits>0</NumUnits>
        <PerUnit>string</PerUnit>
        <SemanticsCode>string</SemanticsCode>
        <SemanticsVendorType>string</SemanticsVendorType>
        <StartDateLocal>string</StartDateLocal>
        <Vendor>string</Vendor>
        <VendorChargeCode>string</VendorChargeCode>
      </RateWithAllowance>
    </Charges>
    <DateBookedLocal>string</DateBookedLocal>
    <DateCreatedUtc>string</DateCreatedUtc>
    <DateModifiedUtc>string</DateModifiedUtc>
    <Delivery>
      <AddressLine1>string</AddressLine1>
      <AddressLine2>string</AddressLine2>
      <City>string</City>
      <Country>string</Country>
      <Email>string</Email>
      <Latitude>0</Latitude>
      <LocationAdditionalDetails>string</LocationAdditionalDetails>
      <LocationDesc>string</LocationDesc>
      <LocationName>string</LocationName>
      <Longitude>0</Longitude>
      <PhoneNumber>string</PhoneNumber>
      <ReferenceNumber>string</ReferenceNumber>
      <State>string</State>
      <Type>string</Type>
      <Zip>string</Zip>
    </Delivery>
    <FormOfPaymentName>string</FormOfPaymentName>
    <FormOfPaymentType>string</FormOfPaymentType>
    <IsGhostCard>true</IsGhostCard>
    <ItinSourceName>string</ItinSourceName>
    <LastTicketDateUtc>string</LastTicketDateUtc>
    <MiscChargeOrders>
      <DateCreatedUtc>string</DateCreatedUtc>
      <DateModifiedUtc>string</DateModifiedUtc>
      <IssueDate>string</IssueDate>
      <PlatingCarrierNumericCode>string</PlatingCarrierNumericCode>
      <PlatingControlNumber>string</PlatingControlNumber>
      <TotalAmount>0</TotalAmount>
      <TotalAmountCurrency>string</TotalAmountCurrency>
    </MiscChargeOrders>
    <PassPrograms>
      <Amount>0</Amount>
      <Name>string</Name>
      <Type>string</Type>
      <UserFirstName>string</UserFirstName>
      <UserLastName>string</UserLastName>
    </PassPrograms>
    <Passengers>
      <City>string</City>
      <Country>string</Country>
      <FirstNameNumber>0</FirstNameNumber>
      <FrequentTravelerPrograms>
        <FrequentFlyer>
          <AirlineVendor>string</AirlineVendor>
          <Description>string</Description>
          <DiscountProgramExpirationDate>string</DiscountProgramExpirationDate>
          <DiscountProgramType>string</DiscountProgramType>
          <FrequentFlyerNumber>string</FrequentFlyerNumber>
          <Status>string</Status>
          <StatusExpirationDate>string</StatusExpirationDate>
        </FrequentFlyer>
        <RailProgram>
          <Description>string</Description>
          <DiscountProgramExpirationDate>string</DiscountProgramExpirationDate>
          <DiscountProgramType>string</DiscountProgramType>
          <ProgramNumber>string</ProgramNumber>
          <Status>string</Status>
          <StatusExpirationDate>string</StatusExpirationDate>
        </RailProgram>
      </FrequentTravelerPrograms>
      <LastNameNumber>0</LastNameNumber>
      <NameFirst>string</NameFirst>
      <NameLast>string</NameLast>
      <NameMiddle>string</NameMiddle>
      <NamePrefix>string</NamePrefix>
      <NameRemark>string</NameRemark>
      <NameSuffix>string</NameSuffix>
      <NameTitle>string</NameTitle>
      <PostalCode>string</PostalCode>
      <State>string</State>
      <StreetAddress>string</StreetAddress>
      <StreetAddress2>string</StreetAddress2>
      <TextName>string</TextName>
    </Passengers>
    <PhoneNumbers>
      <Description>string</Description>
      <PassengerRPH>0</PassengerRPH>
      <PhoneNumber>string</PhoneNumber>
      <Type>string</Type>
    </PhoneNumbers>
    <RailPayments>
      <RailAdjustment>
        <AdjustmentDateTime>string</AdjustmentDateTime>
        <AdjustmentDateTimeUTC>string</AdjustmentDateTimeUTC>
        <AdjustmentType>string</AdjustmentType>
        <DateCreatedUtc>string</DateCreatedUtc>
        <DateModifiedUtc>string</DateModifiedUtc>
        <RailCharges>
          <Fixed>
            <Amount>0</Amount>
            <Currency>string</Currency>
            <Description>string</Description>
            <IsPaid>true</IsPaid>
            <IsPrimary>true</IsPrimary>
            <SemanticsCode>string</SemanticsCode>
            <SemanticsVendorType>string</SemanticsVendorType>
            <StartDateLocal>string</StartDateLocal>
            <Vendor>string</Vendor>
            <VendorChargeCode>string</VendorChargeCode>
          </Fixed>
          <Percent>
            <Amount>0</Amount>
            <Currency>string</Currency>
            <Description>string</Description>
            <IsPaid>true</IsPaid>
            <IsPrimary>true</IsPrimary>
            <SemanticsCode>string</SemanticsCode>
            <SemanticsVendorType>string</SemanticsVendorType>
            <StartDateLocal>string</StartDateLocal>
            <Vendor>string</Vendor>
            <VendorChargeCode>string</VendorChargeCode>
          </Percent>
          <Rate>
            <Amount>0</Amount>
            <Currency>string</Currency>
            <Description>string</Description>
            <IsPaid>true</IsPaid>
            <IsPrimary>true</IsPrimary>
            <NumUnits>0</NumUnits>
            <PerUnit>string</PerUnit>
            <SemanticsCode>string</SemanticsCode>
            <SemanticsVendorType>string</SemanticsVendorType>
            <StartDateLocal>string</StartDateLocal>
            <Vendor>string</Vendor>
            <VendorChargeCode>string</VendorChargeCode>
          </Rate>
          <RateWithAllowance>
            <AllowanceAmount>0</AllowanceAmount>
            <AllowanceIsUnlimited>true</AllowanceIsUnlimited>
            <AllowanceNumUnits>0</AllowanceNumUnits>
            <AllowanceUnit>string</AllowanceUnit>
            <Amount>0</Amount>
            <Currency>string</Currency>
            <Description>string</Description>
            <IsPaid>true</IsPaid>
            <IsPrimary>true</IsPrimary>
            <NumUnits>0</NumUnits>
            <PerUnit>string</PerUnit>
            <SemanticsCode>string</SemanticsCode>
            <SemanticsVendorType>string</SemanticsVendorType>
            <StartDateLocal>string</StartDateLocal>
            <Vendor>string</Vendor>
            <VendorChargeCode>string</VendorChargeCode>
          </RateWithAllowance>
        </RailCharges>
        <Taxes>
          <TaxAmount>0</TaxAmount>
          <TaxAuthority>string</TaxAuthority>
          <TaxName>string</TaxName>
          <TaxRate>0</TaxRate>
          <TaxType>string</TaxType>
        </Taxes>
        <TicketDocumentIdentifier>string</TicketDocumentIdentifier>
        <TotalAdjustment>0</TotalAdjustment>
        <TotalAdjustmentCurrency>string</TotalAdjustmentCurrency>
      </RailAdjustment>
      <RailPayment>
        <BaseFare>0</BaseFare>
        <BaseFareCurrency>string</BaseFareCurrency>
        <DateCreatedUtc>string</DateCreatedUtc>
        <DateModifiedUtc>string</DateModifiedUtc>
        <IncludesVAT>true</IncludesVAT>
        <IssueByDate>string</IssueByDate>
        <IssueDateTime>string</IssueDateTime>
        <IssueDateTimeUTC>string</IssueDateTimeUTC>
        <RailCharges>
          <Fixed>
            <Amount>0</Amount>
            <Currency>string</Currency>
            <Description>string</Description>
            <IsPaid>true</IsPaid>
            <IsPrimary>true</IsPrimary>
            <SemanticsCode>string</SemanticsCode>
            <SemanticsVendorType>string</SemanticsVendorType>
            <StartDateLocal>string</StartDateLocal>
            <Vendor>string</Vendor>
            <VendorChargeCode>string</VendorChargeCode>
          </Fixed>
          <Percent>
            <Amount>0</Amount>
            <Currency>string</Currency>
            <Description>string</Description>
            <IsPaid>true</IsPaid>
            <IsPrimary>true</IsPrimary>
            <SemanticsCode>string</SemanticsCode>
            <SemanticsVendorType>string</SemanticsVendorType>
            <StartDateLocal>string</StartDateLocal>
            <Vendor>string</Vendor>
            <VendorChargeCode>string</VendorChargeCode>
          </Percent>
          <Rate>
            <Amount>0</Amount>
            <Currency>string</Currency>
            <Description>string</Description>
            <IsPaid>true</IsPaid>
            <IsPrimary>true</IsPrimary>
            <NumUnits>0</NumUnits>
            <PerUnit>string</PerUnit>
            <SemanticsCode>string</SemanticsCode>
            <SemanticsVendorType>string</SemanticsVendorType>
            <StartDateLocal>string</StartDateLocal>
            <Vendor>string</Vendor>
            <VendorChargeCode>string</VendorChargeCode>
          </Rate>
          <RateWithAllowance>
            <AllowanceAmount>0</AllowanceAmount>
            <AllowanceIsUnlimited>true</AllowanceIsUnlimited>
            <AllowanceNumUnits>0</AllowanceNumUnits>
            <AllowanceUnit>string</AllowanceUnit>
            <Amount>0</Amount>
            <Currency>string</Currency>
            <Description>string</Description>
            <IsPaid>true</IsPaid>
            <IsPrimary>true</IsPrimary>
            <NumUnits>0</NumUnits>
            <PerUnit>string</PerUnit>
            <SemanticsCode>string</SemanticsCode>
            <SemanticsVendorType>string</SemanticsVendorType>
            <StartDateLocal>string</StartDateLocal>
            <Vendor>string</Vendor>
            <VendorChargeCode>string</VendorChargeCode>
          </RateWithAllowance>
        </RailCharges>
        <TaxInvoice>true</TaxInvoice>
        <Taxes>
          <TaxAmount>0</TaxAmount>
          <TaxAuthority>string</TaxAuthority>
          <TaxName>string</TaxName>
          <TaxRate>0</TaxRate>
          <TaxType>string</TaxType>
        </Taxes>
        <TicketDocumentIdentifier>string</TicketDocumentIdentifier>
        <TicketType>string</TicketType>
        <TotalFare>0</TotalFare>
        <TotalFareCurrency>string</TotalFareCurrency>
        <vatApplicable>true</vatApplicable>
      </RailPayment>
    </RailPayments>
    <RecordLocator>string</RecordLocator>
    <Remarks>
      <TripLinkRemarks>
        <TripLinkRemark>
          <Text>string</Text>
        </TripLinkRemark>
      </TripLinkRemarks>
    </Remarks>
    <Segments>
      <Air>
        <AircraftCode>string</AircraftCode>
        <Bags>string</Bags>
        <Cabin>string</Cabin>
        <CancellationNumber>string</CancellationNumber>
        <CancellationPolicy>string</CancellationPolicy>
        <CarbonEmissionLbs>0</CarbonEmissionLbs>
        <CarbonModel>0</CarbonModel>
        <Charges>
          <Fixed>
            <Amount>0</Amount>
            <Currency>string</Currency>
            <Description>string</Description>
            <IsPaid>true</IsPaid>
            <IsPrimary>true</IsPrimary>
            <SemanticsCode>string</SemanticsCode>
            <SemanticsVendorType>string</SemanticsVendorType>
            <StartDateLocal>string</StartDateLocal>
            <Vendor>string</Vendor>
            <VendorChargeCode>string</VendorChargeCode>
          </Fixed>
          <Percent>
            <Amount>0</Amount>
            <Currency>string</Currency>
            <Description>string</Description>
            <IsPaid>true</IsPaid>
            <IsPrimary>true</IsPrimary>
            <SemanticsCode>string</SemanticsCode>
            <SemanticsVendorType>string</SemanticsVendorType>
            <StartDateLocal>string</StartDateLocal>
            <Vendor>string</Vendor>
            <VendorChargeCode>string</VendorChargeCode>
          </Percent>
          <Rate>
            <Amount>0</Amount>
            <Currency>string</Currency>
            <Description>string</Description>
            <IsPaid>true</IsPaid>
            <IsPrimary>true</IsPrimary>
            <NumUnits>0</NumUnits>
            <PerUnit>string</PerUnit>
            <SemanticsCode>string</SemanticsCode>
            <SemanticsVendorType>string</SemanticsVendorType>
            <StartDateLocal>string</StartDateLocal>
            <Vendor>string</Vendor>
            <VendorChargeCode>string</VendorChargeCode>
          </Rate>
          <RateWithAllowance>
            <AllowanceAmount>0</AllowanceAmount>
            <AllowanceIsUnlimited>true</AllowanceIsUnlimited>
            <AllowanceNumUnits>0</AllowanceNumUnits>
            <AllowanceUnit>string</AllowanceUnit>
            <Amount>0</Amount>
            <Currency>string</Currency>
            <Description>string</Description>
            <IsPaid>true</IsPaid>
            <IsPrimary>true</IsPrimary>
            <NumUnits>0</NumUnits>
            <PerUnit>string</PerUnit>
            <SemanticsCode>string</SemanticsCode>
            <SemanticsVendorType>string</SemanticsVendorType>
            <StartDateLocal>string</StartDateLocal>
            <Vendor>string</Vendor>
            <VendorChargeCode>string</VendorChargeCode>
          </RateWithAllowance>
        </Charges>
        <CheckedBaggage>string</CheckedBaggage>
        <ClassOfService>string</ClassOfService>
        <ConfirmationNumber>string</ConfirmationNumber>
        <DateCancelledUtc>string</DateCancelledUtc>
        <DateCreatedUtc>string</DateCreatedUtc>
        <DateModifiedUtc>string</DateModifiedUtc>
        <Duration>0</Duration>
        <ETicket>string</ETicket>
        <EndCityCode>string</EndCityCode>
        <EndDateLocal>string</EndDateLocal>
        <EndDateUtc>string</EndDateUtc>
        <EndGate>string</EndGate>
        <EndTerminal>string</EndTerminal>
        <FlightNumber>string</FlightNumber>
        <FrequentTravelerId>string</FrequentTravelerId>
        <IsOpenSegment>true</IsOpenSegment>
        <IsPreferredVendor>0</IsPreferredVendor>
        <IsUpgradeAllowed>true</IsUpgradeAllowed>
        <LegId>0</LegId>
        <Meals>string</Meals>
        <Miles>0</Miles>
        <Notes>string</Notes>
        <NumStops>0</NumStops>
        <OpenSegment>string</OpenSegment>
        <OperatedByFlightNumber>string</OperatedByFlightNumber>
        <OperatedByVendor>string</OperatedByVendor>
        <OperatedByVendorName>string</OperatedByVendorName>
        <Remarks>
          <TripLinkRemarks>
            <TripLinkRemark/>
          </TripLinkRemarks>
        </Remarks>
        <RuleViolations>
          <CompanyReasonCode>string</CompanyReasonCode>
          <CompanyRuleText>string</CompanyRuleText>
          <ViolationReasonCode>0</ViolationReasonCode>
        </RuleViolations>
        <Seats>
          <PassengerRph>0</PassengerRph>
          <SeatNumber>string</SeatNumber>
          <Status>string</Status>
        </Seats>
        <Services>string</Services>
        <SpecialInstructions>string</SpecialInstructions>
        <StartCityCode>string</StartCityCode>
        <StartDateLocal>string</StartDateLocal>
        <StartDateUtc>string</StartDateUtc>
        <StartGate>string</StartGate>
        <StartTerminal>string</StartTerminal>
        <Status>string</Status>
        <TimeZone>string</TimeZone>
        <TimeZoneId>0</TimeZoneId>
        <UpgradedDateTime>string</UpgradedDateTime>
        <Vendor>string</Vendor>
        <VendorFlags>string</VendorFlags>
        <VendorName>string</VendorName>
      </Air>
      <Car>
        <AirCondition>string</AirCondition>
        <Body>string</Body>
        <CancellationNumber>string</CancellationNumber>
        <Charges>
          <Fixed>
            <Amount>0</Amount>
            <Currency>string</Currency>
            <Description>string</Description>
            <IsPaid>true</IsPaid>
            <IsPrimary>true</IsPrimary>
            <SemanticsCode>string</SemanticsCode>
            <SemanticsVendorType>string</SemanticsVendorType>
            <StartDateLocal>string</StartDateLocal>
            <Vendor>string</Vendor>
            <VendorChargeCode>string</VendorChargeCode>
          </Fixed>
          <Percent>
            <Amount>0</Amount>
            <Currency>string</Currency>
            <Description>string</Description>
            <IsPaid>true</IsPaid>
            <IsPrimary>true</IsPrimary>
            <SemanticsCode>string</SemanticsCode>
            <SemanticsVendorType>string</SemanticsVendorType>
            <StartDateLocal>string</StartDateLocal>
            <Vendor>string</Vendor>
            <VendorChargeCode>string</VendorChargeCode>
          </Percent>
          <Rate>
            <Amount>0</Amount>
            <Currency>string</Currency>
            <Description>string</Description>
            <IsPaid>true</IsPaid>
            <IsPrimary>true</IsPrimary>
            <NumUnits>0</NumUnits>
            <PerUnit>string</PerUnit>
            <SemanticsCode>string</SemanticsCode>
            <SemanticsVendorType>string</SemanticsVendorType>
            <StartDateLocal>string</StartDateLocal>
            <Vendor>string</Vendor>
            <VendorChargeCode>string</VendorChargeCode>
          </Rate>
          <RateWithAllowance>
            <AllowanceAmount>0</AllowanceAmount>
            <AllowanceIsUnlimited>true</AllowanceIsUnlimited>
            <AllowanceNumUnits>0</AllowanceNumUnits>
            <AllowanceUnit>string</AllowanceUnit>
            <Amount>0</Amount>
            <Currency>string</Currency>
            <Description>string</Description>
            <IsPaid>true</IsPaid>
            <IsPrimary>true</IsPrimary>
            <NumUnits>0</NumUnits>
            <PerUnit>string</PerUnit>
            <SemanticsCode>string</SemanticsCode>
            <SemanticsVendorType>string</SemanticsVendorType>
            <StartDateLocal>string</StartDateLocal>
            <Vendor>string</Vendor>
            <VendorChargeCode>string</VendorChargeCode>
          </RateWithAllowance>
        </Charges>
        <Class>string</Class>
        <ConfirmationNumber>string</ConfirmationNumber>
        <Currency>string</Currency>
        <DailyRate>0</DailyRate>
        <DateCancelledUtc>string</DateCancelledUtc>
        <DateCreatedUtc>string</DateCreatedUtc>
        <DateModifiedUtc>string</DateModifiedUtc>
        <DiscountCode>string</DiscountCode>
        <DropoffCollectionAddress1>string</DropoffCollectionAddress1>
        <DropoffCollectionAddressType>string</DropoffCollectionAddressType>
        <DropoffCollectionCategory>string</DropoffCollectionCategory>
        <DropoffCollectionCity>string</DropoffCollectionCity>
        <DropoffCollectionCityCode>string</DropoffCollectionCityCode>
        <DropoffCollectionCountry>string</DropoffCollectionCountry>
        <DropoffCollectionLatitude>string</DropoffCollectionLatitude>
        <DropoffCollectionLongitude>string</DropoffCollectionLongitude>
        <DropoffCollectionNumber>string</DropoffCollectionNumber>
        <DropoffCollectionPhoneNumber>string</DropoffCollectionPhoneNumber>
        <DropoffCollectionPostalCode>string</DropoffCollectionPostalCode>
        <DropoffCollectionState>string</DropoffCollectionState>
        <EndAddress>string</EndAddress>
        <EndAddress2>string</EndAddress2>
        <EndCity>string</EndCity>
        <EndCityCode>string</EndCityCode>
        <EndCloseTime>string</EndCloseTime>
        <EndCountry>string</EndCountry>
        <EndDateLocal>string</EndDateLocal>
        <EndDateUtc>string</EndDateUtc>
        <EndLatitude>0</EndLatitude>
        <EndLongitude>0</EndLongitude>
        <EndOpenTime>string</EndOpenTime>
        <EndPhoneNumber>string</EndPhoneNumber>
        <EndPostalCode>string</EndPostalCode>
        <EndState>string</EndState>
        <IsGhostCard>true</IsGhostCard>
        <IsPreferredVendor>0</IsPreferredVendor>
        <IsUpgradeAllowed>true</IsUpgradeAllowed>
        <Notes>string</Notes>
        <NumCars>0</NumCars>
        <NumPersons>0</NumPersons>
        <PhoneNumber>string</PhoneNumber>
        <PickupDeliveryAddress1>string</PickupDeliveryAddress1>
        <PickupDeliveryAddressType>string</PickupDeliveryAddressType>
        <PickupDeliveryCategory>string</PickupDeliveryCategory>
        <PickupDeliveryCity>string</PickupDeliveryCity>
        <PickupDeliveryCityCode>string</PickupDeliveryCityCode>
        <PickupDeliveryCountry>string</PickupDeliveryCountry>
        <PickupDeliveryLatitude>string</PickupDeliveryLatitude>
        <PickupDeliveryLongitude>string</PickupDeliveryLongitude>
        <PickupDeliveryNumber>string</PickupDeliveryNumber>
        <PickupDeliveryPhoneNumber>string</PickupDeliveryPhoneNumber>
        <PickupDeliveryPostalCode>string</PickupDeliveryPostalCode>
        <PickupDeliveryState>string</PickupDeliveryState>
        <RateCode>string</RateCode>
        <RateType>string</RateType>
        <Remarks>
          <TripLinkRemarks>
            <TripLinkRemark/>
          </TripLinkRemarks>
        </Remarks>
        <SpecialEquipment>string</SpecialEquipment>
        <SpecialInstructions>string</SpecialInstructions>
        <StartAddress>string</StartAddress>
        <StartAddress2>string</StartAddress2>
        <StartCity>string</StartCity>
        <StartCityCode>string</StartCityCode>
        <StartCloseTime>string</StartCloseTime>
        <StartCountry>string</StartCountry>
        <StartDateLocal>string</StartDateLocal>
        <StartDateUtc>string</StartDateUtc>
        <StartLatitude>0</StartLatitude>
        <StartLocation>string</StartLocation>
        <StartLongitude>0</StartLongitude>
        <StartOpenTime>string</StartOpenTime>
        <StartPostalCode>string</StartPostalCode>
        <StartState>string</StartState>
        <Status>string</Status>
        <TimeZone>string</TimeZone>
        <TimeZoneId>0</TimeZoneId>
        <TotalRate>0</TotalRate>
        <Transmission>string</Transmission>
        <UpgradedDateTime>string</UpgradedDateTime>
        <Vendor>string</Vendor>
        <VendorFlags>string</VendorFlags>
        <VendorName>string</VendorName>
      </Car>
      <Dining>
        <CancellationNumber>string</CancellationNumber>
        <Charges>
          <Fixed>
            <Amount>0</Amount>
            <Currency>string</Currency>
            <Description>string</Description>
            <IsPaid>true</IsPaid>
            <IsPrimary>true</IsPrimary>
            <SemanticsCode>string</SemanticsCode>
            <SemanticsVendorType>string</SemanticsVendorType>
            <StartDateLocal>string</StartDateLocal>
            <Vendor>string</Vendor>
            <VendorChargeCode>string</VendorChargeCode>
          </Fixed>
          <Percent>
            <Amount>0</Amount>
            <Currency>string</Currency>
            <Description>string</Description>
            <IsPaid>true</IsPaid>
            <IsPrimary>true</IsPrimary>
            <SemanticsCode>string</SemanticsCode>
            <SemanticsVendorType>string</SemanticsVendorType>
            <StartDateLocal>string</StartDateLocal>
            <Vendor>string</Vendor>
            <VendorChargeCode>string</VendorChargeCode>
          </Percent>
          <Rate>
            <Amount>0</Amount>
            <Currency>string</Currency>
            <Description>string</Description>
            <IsPaid>true</IsPaid>
            <IsPrimary>true</IsPrimary>
            <NumUnits>0</NumUnits>
            <PerUnit>string</PerUnit>
            <SemanticsCode>string</SemanticsCode>
            <SemanticsVendorType>string</SemanticsVendorType>
            <StartDateLocal>string</StartDateLocal>
            <Vendor>string</Vendor>
            <VendorChargeCode>string</VendorChargeCode>
          </Rate>
          <RateWithAllowance>
            <AllowanceAmount>0</AllowanceAmount>
            <AllowanceIsUnlimited>true</AllowanceIsUnlimited>
            <AllowanceNumUnits>0</AllowanceNumUnits>
            <AllowanceUnit>string</AllowanceUnit>
            <Amount>0</Amount>
            <Currency>string</Currency>
            <Description>string</Description>
            <IsPaid>true</IsPaid>
            <IsPrimary>true</IsPrimary>
            <NumUnits>0</NumUnits>
            <PerUnit>string</PerUnit>
            <SemanticsCode>string</SemanticsCode>
            <SemanticsVendorType>string</SemanticsVendorType>
            <StartDateLocal>string</StartDateLocal>
            <Vendor>string</Vendor>
            <VendorChargeCode>string</VendorChargeCode>
          </RateWithAllowance>
        </Charges>
        <ConfirmationNumber>string</ConfirmationNumber>
        <DateCancelledUtc>string</DateCancelledUtc>
        <DateCreatedUtc>string</DateCreatedUtc>
        <DateModifiedUtc>string</DateModifiedUtc>
        <EndDateLocal>string</EndDateLocal>
        <EndDateUtc>string</EndDateUtc>
        <FrequentTravelerId>string</FrequentTravelerId>
        <IsPreferredVendor>0</IsPreferredVendor>
        <IsUpgradeAllowed>true</IsUpgradeAllowed>
        <Name>string</Name>
        <Notes>string</Notes>
        <NumPersons>0</NumPersons>
        <PhoneNumber>string</PhoneNumber>
        <Remarks>
          <TripLinkRemarks>
            <TripLinkRemark/>
          </TripLinkRemarks>
        </Remarks>
        <ReservationId>string</ReservationId>
        <StartAddress>string</StartAddress>
        <StartAddress2>string</StartAddress2>
        <StartCity>string</StartCity>
        <StartCountry>string</StartCountry>
        <StartDateLocal>string</StartDateLocal>
        <StartDateUtc>string</StartDateUtc>
        <StartLatitude>0</StartLatitude>
        <StartLongitude>0</StartLongitude>
        <StartPostalCode>string</StartPostalCode>
        <StartState>string</StartState>
        <Status>string</Status>
        <TimeZone>string</TimeZone>
        <TimeZoneId>0</TimeZoneId>
        <UpgradedDateTime>string</UpgradedDateTime>
        <Vendor>string</Vendor>
        <VendorFlags>string</VendorFlags>
        <VendorName>string</VendorName>
      </Dining>
      <Hotel>
        <Breakfast>true</Breakfast>
        <CancellationNumber>string</CancellationNumber>
        <CancellationPolicy>string</CancellationPolicy>
        <Charges>
          <Fixed>
            <Amount>0</Amount>
            <Currency>string</Currency>
            <Description>string</Description>
            <IsPaid>true</IsPaid>
            <IsPrimary>true</IsPrimary>
            <SemanticsCode>string</SemanticsCode>
            <SemanticsVendorType>string</SemanticsVendorType>
            <StartDateLocal>string</StartDateLocal>
            <Vendor>string</Vendor>
            <VendorChargeCode>string</VendorChargeCode>
          </Fixed>
          <Percent>
            <Amount>0</Amount>
            <Currency>string</Currency>
            <Description>string</Description>
            <IsPaid>true</IsPaid>
            <IsPrimary>true</IsPrimary>
            <SemanticsCode>string</SemanticsCode>
            <SemanticsVendorType>string</SemanticsVendorType>
            <StartDateLocal>string</StartDateLocal>
            <Vendor>string</Vendor>
            <VendorChargeCode>string</VendorChargeCode>
          </Percent>
          <Rate>
            <Amount>0</Amount>
            <Currency>string</Currency>
            <Description>string</Description>
            <IsPaid>true</IsPaid>
            <IsPrimary>true</IsPrimary>
            <NumUnits>0</NumUnits>
            <PerUnit>string</PerUnit>
            <SemanticsCode>string</SemanticsCode>
            <SemanticsVendorType>string</SemanticsVendorType>
            <StartDateLocal>string</StartDateLocal>
            <Vendor>string</Vendor>
            <VendorChargeCode>string</VendorChargeCode>
          </Rate>
          <RateWithAllowance>
            <AllowanceAmount>0</AllowanceAmount>
            <AllowanceIsUnlimited>true</AllowanceIsUnlimited>
            <AllowanceNumUnits>0</AllowanceNumUnits>
            <AllowanceUnit>string</AllowanceUnit>
            <Amount>0</Amount>
            <Currency>string</Currency>
            <Description>string</Description>
            <IsPaid>true</IsPaid>
            <IsPrimary>true</IsPrimary>
            <NumUnits>0</NumUnits>
            <PerUnit>string</PerUnit>
            <SemanticsCode>string</SemanticsCode>
            <SemanticsVendorType>string</SemanticsVendorType>
            <StartDateLocal>string</StartDateLocal>
            <Vendor>string</Vendor>
            <VendorChargeCode>string</VendorChargeCode>
          </RateWithAllowance>
        </Charges>
        <CheckinTime>string</CheckinTime>
        <CheckoutTime>string</CheckoutTime>
        <ConfirmationNumber>string</ConfirmationNumber>
        <Currency>string</Currency>
        <DailyRate>0</DailyRate>
        <DateCancelledUtc>string</DateCancelledUtc>
        <DateCreatedUtc>string</DateCreatedUtc>
        <DateModifiedUtc>string</DateModifiedUtc>
        <DirectBill>true</DirectBill>
        <DiscountCode>string</DiscountCode>
        <Email>string</Email>
        <EndDateLocal>string</EndDateLocal>
        <EndDateUtc>string</EndDateUtc>
        <EquipmentCode>string</EquipmentCode>
        <FaxNumber>string</FaxNumber>
        <FrequentTravelerId>string</FrequentTravelerId>
        <HotelPropertyId>string</HotelPropertyId>
        <IncludedCustomAmenities>string</IncludedCustomAmenities>
        <IsGhostCard>true</IsGhostCard>
        <IsPreferredVendor>0</IsPreferredVendor>
        <IsUpgradeAllowed>true</IsUpgradeAllowed>
        <ModificationCode>string</ModificationCode>
        <Name>string</Name>
        <Notes>string</Notes>
        <NumPersons>0</NumPersons>
        <NumRooms>0</NumRooms>
        <Parking>true</Parking>
        <PartnerMembershipId>string</PartnerMembershipId>
        <PassiveType>string</PassiveType>
        <PhoneNumber>string</PhoneNumber>
        <RateAccess>string</RateAccess>
        <RateCode>string</RateCode>
        <RateType>string</RateType>
        <Remarks>
          <TripLinkRemarks>
            <TripLinkRemark/>
          </TripLinkRemarks>
        </Remarks>
        <RoomDescription>string</RoomDescription>
        <RoomType>string</RoomType>
        <SpecialInstructions>string</SpecialInstructions>
        <StartAddress>string</StartAddress>
        <StartAddress2>string</StartAddress2>
        <StartCity>string</StartCity>
        <StartCityCode>string</StartCityCode>
        <StartCountry>string</StartCountry>
        <StartDateLocal>string</StartDateLocal>
        <StartDateUtc>string</StartDateUtc>
        <StartLatitude>0</StartLatitude>
        <StartLongitude>0</StartLongitude>
        <StartPostalCode>string</StartPostalCode>
        <StartState>string</StartState>
        <Status>string</Status>
        <TimeZone>string</TimeZone>
        <TimeZoneId>0</TimeZoneId>
        <TotalRate>0</TotalRate>
        <UpgradedDateTime>string</UpgradedDateTime>
        <Vendor>string</Vendor>
        <VendorFlags>string</VendorFlags>
        <VendorName>string</VendorName>
        <Wifi>true</Wifi>
      </Hotel>
      <Parking>
        <CancellationNumber>string</CancellationNumber>
        <Charges>
          <Fixed>
            <Amount>0</Amount>
            <Currency>string</Currency>
            <Description>string</Description>
            <IsPaid>true</IsPaid>
            <IsPrimary>true</IsPrimary>
            <SemanticsCode>string</SemanticsCode>
            <SemanticsVendorType>string</SemanticsVendorType>
            <StartDateLocal>string</StartDateLocal>
            <Vendor>string</Vendor>
            <VendorChargeCode>string</VendorChargeCode>
          </Fixed>
          <Percent>
            <Amount>0</Amount>
            <Currency>string</Currency>
            <Description>string</Description>
            <IsPaid>true</IsPaid>
            <IsPrimary>true</IsPrimary>
            <SemanticsCode>string</SemanticsCode>
            <SemanticsVendorType>string</SemanticsVendorType>
            <StartDateLocal>string</StartDateLocal>
            <Vendor>string</Vendor>
            <VendorChargeCode>string</VendorChargeCode>
          </Percent>
          <Rate>
            <Amount>0</Amount>
            <Currency>string</Currency>
            <Description>string</Description>
            <IsPaid>true</IsPaid>
            <IsPrimary>true</IsPrimary>
            <NumUnits>0</NumUnits>
            <PerUnit>string</PerUnit>
            <SemanticsCode>string</SemanticsCode>
            <SemanticsVendorType>string</SemanticsVendorType>
            <StartDateLocal>string</StartDateLocal>
            <Vendor>string</Vendor>
            <VendorChargeCode>string</VendorChargeCode>
          </Rate>
          <RateWithAllowance>
            <AllowanceAmount>0</AllowanceAmount>
            <AllowanceIsUnlimited>true</AllowanceIsUnlimited>
            <AllowanceNumUnits>0</AllowanceNumUnits>
            <AllowanceUnit>string</AllowanceUnit>
            <Amount>0</Amount>
            <Currency>string</Currency>
            <Description>string</Description>
            <IsPaid>true</IsPaid>
            <IsPrimary>true</IsPrimary>
            <NumUnits>0</NumUnits>
            <PerUnit>string</PerUnit>
            <SemanticsCode>string</SemanticsCode>
            <SemanticsVendorType>string</SemanticsVendorType>
            <StartDateLocal>string</StartDateLocal>
            <Vendor>string</Vendor>
            <VendorChargeCode>string</VendorChargeCode>
          </RateWithAllowance>
        </Charges>
        <ClassOfService>string</ClassOfService>
        <ConfirmationNumber>string</ConfirmationNumber>
        <Currency>string</Currency>
        <DateCancelledUtc>string</DateCancelledUtc>
        <DateCreatedUtc>string</DateCreatedUtc>
        <DateModifiedUtc>string</DateModifiedUtc>
        <EndDateLocal>string</EndDateLocal>
        <EndDateUtc>string</EndDateUtc>
        <FrequentTravelerId>string</FrequentTravelerId>
        <IsPreferredVendor>0</IsPreferredVendor>
        <IsUpgradeAllowed>true</IsUpgradeAllowed>
        <Name>string</Name>
        <Notes>string</Notes>
        <OperatedByVendor>string</OperatedByVendor>
        <ParkingLocationId>string</ParkingLocationId>
        <PhoneNumber>string</PhoneNumber>
        <Pin>string</Pin>
        <RateCode>string</RateCode>
        <Remarks>
          <TripLinkRemarks>
            <TripLinkRemark/>
          </TripLinkRemarks>
        </Remarks>
        <StartAddress>string</StartAddress>
        <StartAddress2>string</StartAddress2>
        <StartCity>string</StartCity>
        <StartCityCode>string</StartCityCode>
        <StartCountry>string</StartCountry>
        <StartDateLocal>string</StartDateLocal>
        <StartDateUtc>string</StartDateUtc>
        <StartLocation>string</StartLocation>
        <StartPostalCode>string</StartPostalCode>
        <StartState>string</StartState>
        <Status>string</Status>
        <TimeZone>string</TimeZone>
        <TimeZoneId>0</TimeZoneId>
        <TotalRate>0</TotalRate>
        <UpgradedDateTime>string</UpgradedDateTime>
        <Vendor>string</Vendor>
        <VendorFlags>string</VendorFlags>
        <VendorName>string</VendorName>
      </Parking>
      <Rail>
        <Amenities>string</Amenities>
        <Cabin>string</Cabin>
        <CancellationNumber>string</CancellationNumber>
        <CarbonEmissionLbs>0</CarbonEmissionLbs>
        <CarbonModel>0</CarbonModel>
        <Charges>
          <Fixed>
            <Amount>0</Amount>
            <Currency>string</Currency>
            <Description>string</Description>
            <IsPaid>true</IsPaid>
            <IsPrimary>true</IsPrimary>
            <SemanticsCode>string</SemanticsCode>
            <SemanticsVendorType>string</SemanticsVendorType>
            <StartDateLocal>string</StartDateLocal>
            <Vendor>string</Vendor>
            <VendorChargeCode>string</VendorChargeCode>
          </Fixed>
          <Percent>
            <Amount>0</Amount>
            <Currency>string</Currency>
            <Description>string</Description>
            <IsPaid>true</IsPaid>
            <IsPrimary>true</IsPrimary>
            <SemanticsCode>string</SemanticsCode>
            <SemanticsVendorType>string</SemanticsVendorType>
            <StartDateLocal>string</StartDateLocal>
            <Vendor>string</Vendor>
            <VendorChargeCode>string</VendorChargeCode>
          </Percent>
          <Rate>
            <Amount>0</Amount>
            <Currency>string</Currency>
            <Description>string</Description>
            <IsPaid>true</IsPaid>
            <IsPrimary>true</IsPrimary>
            <NumUnits>0</NumUnits>
            <PerUnit>string</PerUnit>
            <SemanticsCode>string</SemanticsCode>
            <SemanticsVendorType>string</SemanticsVendorType>
            <StartDateLocal>string</StartDateLocal>
            <Vendor>string</Vendor>
            <VendorChargeCode>string</VendorChargeCode>
          </Rate>
          <RateWithAllowance>
            <AllowanceAmount>0</AllowanceAmount>
            <AllowanceIsUnlimited>true</AllowanceIsUnlimited>
            <AllowanceNumUnits>0</AllowanceNumUnits>
            <AllowanceUnit>string</AllowanceUnit>
            <Amount>0</Amount>
            <Currency>string</Currency>
            <Description>string</Description>
            <IsPaid>true</IsPaid>
            <IsPrimary>true</IsPrimary>
            <NumUnits>0</NumUnits>
            <PerUnit>string</PerUnit>
            <SemanticsCode>string</SemanticsCode>
            <SemanticsVendorType>string</SemanticsVendorType>
            <StartDateLocal>string</StartDateLocal>
            <Vendor>string</Vendor>
            <VendorChargeCode>string</VendorChargeCode>
          </RateWithAllowance>
        </Charges>
        <ClassOfService>string</ClassOfService>
        <ConfirmationNumber>string</ConfirmationNumber>
        <Currency>string</Currency>
        <DateCancelledUtc>string</DateCancelledUtc>
        <DateCreatedUtc>string</DateCreatedUtc>
        <DateModifiedUtc>string</DateModifiedUtc>
        <DiscountCode>string</DiscountCode>
        <Duration>0</Duration>
        <ETicket>string</ETicket>
        <EndCity>string</EndCity>
        <EndCityCode>string</EndCityCode>
        <EndCountry>string</EndCountry>
        <EndDateLocal>string</EndDateLocal>
        <EndDateUtc>string</EndDateUtc>
        <EndLatitude>0</EndLatitude>
        <EndLongitude>0</EndLongitude>
        <EndPlatform>string</EndPlatform>
        <EndRailStation>string</EndRailStation>
        <EndRailStationName>string</EndRailStationName>
        <EndState>string</EndState>
        <FrequentTravelerId>string</FrequentTravelerId>
        <IsPreferredVendor>0</IsPreferredVendor>
        <IsUpgradeAllowed>true</IsUpgradeAllowed>
        <LegId>0</LegId>
        <Meals>string</Meals>
        <Miles>0</Miles>
        <Notes>string</Notes>
        <NumPersons>0</NumPersons>
        <NumStops>0</NumStops>
        <OperatedByTrainNumber>string</OperatedByTrainNumber>
        <OperatedByVendor>string</OperatedByVendor>
        <RateCode>string</RateCode>
        <Remarks>
          <TripLinkRemarks>
            <TripLinkRemark/>
          </TripLinkRemarks>
        </Remarks>
        <RouteRestrictCode>string</RouteRestrictCode>
        <Seats>
          <Amenities>string</Amenities>
          <BerthPosition>string</BerthPosition>
          <Deck>string</Deck>
          <FacingForward>string</FacingForward>
          <FareSpaceComfort>string</FareSpaceComfort>
          <PassengerRph>0</PassengerRph>
          <SeatNumber>string</SeatNumber>
          <SeatPosition>string</SeatPosition>
          <SeatType>string</SeatType>
          <SpaceType>string</SpaceType>
          <Status>string</Status>
          <WagonNumber>string</WagonNumber>
          <WagonType>string</WagonType>
        </Seats>
        <SpecialInstructions>string</SpecialInstructions>
        <StartCity>string</StartCity>
        <StartCityCode>string</StartCityCode>
        <StartCountry>string</StartCountry>
        <StartDateLocal>string</StartDateLocal>
        <StartDateUtc>string</StartDateUtc>
        <StartLatitude>0</StartLatitude>
        <StartLongitude>0</StartLongitude>
        <StartPlatform>string</StartPlatform>
        <StartRailStation>string</StartRailStation>
        <StartRailStationName>string</StartRailStationName>
        <StartState>string</StartState>
        <Status>string</Status>
        <TimeZone>string</TimeZone>
        <TimeZoneId>0</TimeZoneId>
        <TotalRate>0</TotalRate>
        <TrainNumber>string</TrainNumber>
        <TrainTypeCode>string</TrainTypeCode>
        <TrainTypeName>string</TrainTypeName>
        <TransportMode>string</TransportMode>
        <UpgradedDateTime>string</UpgradedDateTime>
        <Vendor>string</Vendor>
        <VendorFlags>string</VendorFlags>
        <VendorName>string</VendorName>
        <WagonNumber>string</WagonNumber>
      </Rail>
      <Ride>
        <CancellationNumber>string</CancellationNumber>
        <CancellationPolicy>string</CancellationPolicy>
        <Charges>
          <Fixed>
            <Amount>0</Amount>
            <Currency>string</Currency>
            <Description>string</Description>
            <IsPaid>true</IsPaid>
            <IsPrimary>true</IsPrimary>
            <SemanticsCode>string</SemanticsCode>
            <SemanticsVendorType>string</SemanticsVendorType>
            <StartDateLocal>string</StartDateLocal>
            <Vendor>string</Vendor>
            <VendorChargeCode>string</VendorChargeCode>
          </Fixed>
          <Percent>
            <Amount>0</Amount>
            <Currency>string</Currency>
            <Description>string</Description>
            <IsPaid>true</IsPaid>
            <IsPrimary>true</IsPrimary>
            <SemanticsCode>string</SemanticsCode>
            <SemanticsVendorType>string</SemanticsVendorType>
            <StartDateLocal>string</StartDateLocal>
            <Vendor>string</Vendor>
            <VendorChargeCode>string</VendorChargeCode>
          </Percent>
          <Rate>
            <Amount>0</Amount>
            <Currency>string</Currency>
            <Description>string</Description>
            <IsPaid>true</IsPaid>
            <IsPrimary>true</IsPrimary>
            <NumUnits>0</NumUnits>
            <PerUnit>string</PerUnit>
            <SemanticsCode>string</SemanticsCode>
            <SemanticsVendorType>string</SemanticsVendorType>
            <StartDateLocal>string</StartDateLocal>
            <Vendor>string</Vendor>
            <VendorChargeCode>string</VendorChargeCode>
          </Rate>
          <RateWithAllowance>
            <AllowanceAmount>0</AllowanceAmount>
            <AllowanceIsUnlimited>true</AllowanceIsUnlimited>
            <AllowanceNumUnits>0</AllowanceNumUnits>
            <AllowanceUnit>string</AllowanceUnit>
            <Amount>0</Amount>
            <Currency>string</Currency>
            <Description>string</Description>
            <IsPaid>true</IsPaid>
            <IsPrimary>true</IsPrimary>
            <NumUnits>0</NumUnits>
            <PerUnit>string</PerUnit>
            <SemanticsCode>string</SemanticsCode>
            <SemanticsVendorType>string</SemanticsVendorType>
            <StartDateLocal>string</StartDateLocal>
            <Vendor>string</Vendor>
            <VendorChargeCode>string</VendorChargeCode>
          </RateWithAllowance>
        </Charges>
        <ConfirmationNumber>string</ConfirmationNumber>
        <Currency>string</Currency>
        <DateCancelledUtc>string</DateCancelledUtc>
        <DateCreatedUtc>string</DateCreatedUtc>
        <DateModifiedUtc>string</DateModifiedUtc>
        <DropoffInstructions>string</DropoffInstructions>
        <Duration>0</Duration>
        <EndAddress>string</EndAddress>
        <EndAddress2>string</EndAddress2>
        <EndCity>string</EndCity>
        <EndCityCode>string</EndCityCode>
        <EndCountry>string</EndCountry>
        <EndDateLocal>string</EndDateLocal>
        <EndDateUtc>string</EndDateUtc>
        <EndLatitude>0</EndLatitude>
        <EndLocationCode>string</EndLocationCode>
        <EndLongitude>0</EndLongitude>
        <EndPostalCode>string</EndPostalCode>
        <EndState>string</EndState>
        <IsGhostCard>true</IsGhostCard>
        <IsPreferredVendor>0</IsPreferredVendor>
        <IsUpgradeAllowed>true</IsUpgradeAllowed>
        <MeetingInstructions>string</MeetingInstructions>
        <Miles>0</Miles>
        <Name>string</Name>
        <Notes>string</Notes>
        <NumPersons>0</NumPersons>
        <NumberOfHours>0</NumberOfHours>
        <OperatedByVendorName>string</OperatedByVendorName>
        <PassiveCityCode>string</PassiveCityCode>
        <PhoneNumber>string</PhoneNumber>
        <PickupInstructions>string</PickupInstructions>
        <ProviderFeedback>string</ProviderFeedback>
        <Rate>0</Rate>
        <RateDescription>string</RateDescription>
        <RateNotes>string</RateNotes>
        <RateType>string</RateType>
        <Remarks>
          <TripLinkRemarks>
            <TripLinkRemark/>
          </TripLinkRemarks>
        </Remarks>
        <ReservationId>string</ReservationId>
        <SpecialInstructions>string</SpecialInstructions>
        <StartAddress>string</StartAddress>
        <StartAddress2>string</StartAddress2>
        <StartCity>string</StartCity>
        <StartCityCode>string</StartCityCode>
        <StartCountry>string</StartCountry>
        <StartDateLocal>string</StartDateLocal>
        <StartDateUtc>string</StartDateUtc>
        <StartLatitude>0</StartLatitude>
        <StartLocation>string</StartLocation>
        <StartLocationCode>string</StartLocationCode>
        <StartLocationName>string</StartLocationName>
        <StartLongitude>0</StartLongitude>
        <StartPostalCode>string</StartPostalCode>
        <StartState>string</StartState>
        <TimeZone>string</TimeZone>
        <TimeZoneId>0</TimeZoneId>
        <TotalRate>0</TotalRate>
        <UpgradedDateTime>string</UpgradedDateTime>
        <Vendor>string</Vendor>
        <VendorFlags>string</VendorFlags>
        <VendorName>string</VendorName>
      </Ride>
      <Travel>
        <CancellationNumber>string</CancellationNumber>
        <Charges>
          <Fixed>
            <Amount>0</Amount>
            <Currency>string</Currency>
            <Description>string</Description>
            <IsPaid>true</IsPaid>
            <IsPrimary>true</IsPrimary>
            <SemanticsCode>string</SemanticsCode>
            <SemanticsVendorType>string</SemanticsVendorType>
            <StartDateLocal>string</StartDateLocal>
            <Vendor>string</Vendor>
            <VendorChargeCode>string</VendorChargeCode>
          </Fixed>
          <Percent>
            <Amount>0</Amount>
            <Currency>string</Currency>
            <Description>string</Description>
            <IsPaid>true</IsPaid>
            <IsPrimary>true</IsPrimary>
            <SemanticsCode>string</SemanticsCode>
            <SemanticsVendorType>string</SemanticsVendorType>
            <StartDateLocal>string</StartDateLocal>
            <Vendor>string</Vendor>
            <VendorChargeCode>string</VendorChargeCode>
          </Percent>
          <Rate>
            <Amount>0</Amount>
            <Currency>string</Currency>
            <Description>string</Description>
            <IsPaid>true</IsPaid>
            <IsPrimary>true</IsPrimary>
            <NumUnits>0</NumUnits>
            <PerUnit>string</PerUnit>
            <SemanticsCode>string</SemanticsCode>
            <SemanticsVendorType>string</SemanticsVendorType>
            <StartDateLocal>string</StartDateLocal>
            <Vendor>string</Vendor>
            <VendorChargeCode>string</VendorChargeCode>
          </Rate>
          <RateWithAllowance>
            <AllowanceAmount>0</AllowanceAmount>
            <AllowanceIsUnlimited>true</AllowanceIsUnlimited>
            <AllowanceNumUnits>0</AllowanceNumUnits>
            <AllowanceUnit>string</AllowanceUnit>
            <Amount>0</Amount>
            <Currency>string</Currency>
            <Description>string</Description>
            <IsPaid>true</IsPaid>
            <IsPrimary>true</IsPrimary>
            <NumUnits>0</NumUnits>
            <PerUnit>string</PerUnit>
            <SemanticsCode>string</SemanticsCode>
            <SemanticsVendorType>string</SemanticsVendorType>
            <StartDateLocal>string</StartDateLocal>
            <Vendor>string</Vendor>
            <VendorChargeCode>string</VendorChargeCode>
          </RateWithAllowance>
        </Charges>
        <ConfirmationNumber>string</ConfirmationNumber>
        <Currency>string</Currency>
        <DailyRate>0</DailyRate>
        <DateCancelledUtc>string</DateCancelledUtc>
        <DateCreatedUtc>string</DateCreatedUtc>
        <DateModifiedUtc>string</DateModifiedUtc>
        <EndAddress>string</EndAddress>
        <EndAddress2>string</EndAddress2>
        <EndCity>string</EndCity>
        <EndCityCode>string</EndCityCode>
        <EndCountry>string</EndCountry>
        <EndDateLocal>string</EndDateLocal>
        <EndDateUtc>string</EndDateUtc>
        <EndLatitude>0</EndLatitude>
        <EndLocation>string</EndLocation>
        <EndLongitude>0</EndLongitude>
        <EndPostalCode>string</EndPostalCode>
        <EndState>string</EndState>
        <IsGhostCard>true</IsGhostCard>
        <Notes>string</Notes>
        <NumPersons>0</NumPersons>
        <PhoneNumber>string</PhoneNumber>
        <Remarks>
          <TripLinkRemarks>
            <TripLinkRemark/>
          </TripLinkRemarks>
        </Remarks>
        <SpecialInstructions>string</SpecialInstructions>
        <StartAddress>string</StartAddress>
        <StartAddress2>string</StartAddress2>
        <StartCity>string</StartCity>
        <StartCityCode>string</StartCityCode>
        <StartCountry>string</StartCountry>
        <StartDateLocal>string</StartDateLocal>
        <StartDateUtc>string</StartDateUtc>
        <StartLatitude>0</StartLatitude>
        <StartLocation>string</StartLocation>
        <StartLongitude>0</StartLongitude>
        <StartPostalCode>string</StartPostalCode>
        <StartState>string</StartState>
        <Status>string</Status>
        <TimeZone>string</TimeZone>
        <TimeZoneId>0</TimeZoneId>
        <TotalRate>0</TotalRate>
        <TransportMode>string</TransportMode>
        <Vendor>string</Vendor>
        <VendorName>string</VendorName>
      </Travel>
    </Segments>
    <TicketMailingAddress>string</TicketMailingAddress>
    <TicketPickupLocation>string</TicketPickupLocation>
    <TicketPickupNumber>string</TicketPickupNumber>
    <WaitListSegments>
      <SegmentOption>
        <Flight>
          <ArrAirp>string</ArrAirp>
          <Cabin>string</Cabin>
          <Carrier>string</Carrier>
          <DepAirp>string</DepAirp>
          <FlightNum>string</FlightNum>
        </Flight>
        <SegmentIndex>string</SegmentIndex>
        <StatusCode>string</StatusCode>
        <TimeStamp>string</TimeStamp>
      </SegmentOption>
    </WaitListSegments>
    <Warnings>
      <Code>string</Code>
      <Text>string</Text>
      <Type>string</Type>
    </Warnings>
    <WebAddresses>
      <Description>string</Description>
      <Format>string</Format>
      <PassengerRPH>0</PassengerRPH>
      <Type>string</Type>
      <WebAddress>string</WebAddress>
    </WebAddresses>
  </Bookings>
  <CancelComments>string</CancelComments>
  <ClientLocator>string</ClientLocator>
  <Comments>string</Comments>
  <CustomAttributes>
    <Data>string</Data>
    <DataType>string</DataType>
    <DisplayOnItinerary>true</DisplayOnItinerary>
    <DisplayTitle>string</DisplayTitle>
    <ExternalId>0</ExternalId>
    <Name>string</Name>
  </CustomAttributes>
  <DateBookedLocal>string</DateBookedLocal>
  <DateCreatedUtc>string</DateCreatedUtc>
  <DateModifiedUtc>string</DateModifiedUtc>
  <Description>string</Description>
  <EndDateLocal>string</EndDateLocal>
  <EndDateUtc>string</EndDateUtc>
  <HasOpenBookingPassive>true</HasOpenBookingPassive>
  <IsPersonal>true</IsPersonal>
  <ItinLocator>string</ItinLocator>
  <ProjectName>string</ProjectName>
  <StartDateLocal>string</StartDateLocal>
  <StartDateUtc>string</StartDateUtc>
  <TravelRequestId>string</TravelRequestId>
  <TripLinkLocator>string</TripLinkLocator>
  <TripName>string</TripName>
  <TripStatus>0</TripStatus>
  <UserLoginId>string</UserLoginId>
  <id>string</id>
</Itinerary>
```

<h3 id="get__trips_{tripid}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[Itinerary](#schemaitinerary)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[model.ErrorAPIResponse](#schemamodel.errorapiresponse)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[model.ErrorAPIResponse](#schemamodel.errorapiresponse)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|ID Not Found|[model.ErrorAPIResponse](#schemamodel.errorapiresponse)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[model.ErrorAPIResponse](#schemamodel.errorapiresponse)|

<aside class="success">
This operation does not require authentication
</aside>

# Schemas

<h2 id="tocS_AccountingLine">AccountingLine</h2>
<!-- backwards compatibility -->
<a id="schemaaccountingline"></a>
<a id="schema_AccountingLine"></a>
<a id="tocSaccountingline"></a>
<a id="tocsaccountingline"></a>

```json
{
  "AirlineCode": "string",
  "AmountPaid": "string",
  "AmountPaidCurrency": "string",
  "CCNumber": "string",
  "Comment": "string",
  "Commission": "string",
  "CommissionCurrency": "string",
  "ExchangedTicketNumber": "string",
  "FOPMethod": "string",
  "Fare": "string",
  "FareCurrency": "string",
  "IssueDate": "string",
  "MCOType": "string",
  "Tax": "string",
  "TaxCurrency": "string",
  "TranControlNbr": "string",
  "TranPlatingNbr": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|AirlineCode|string|false|none|none|
|AmountPaid|string|false|none|none|
|AmountPaidCurrency|string|false|none|none|
|CCNumber|string|false|none|none|
|Comment|string|false|none|none|
|Commission|string|false|none|none|
|CommissionCurrency|string|false|none|none|
|ExchangedTicketNumber|string|false|none|none|
|FOPMethod|string|false|none|none|
|Fare|string|false|none|none|
|FareCurrency|string|false|none|none|
|IssueDate|string|false|none|none|
|MCOType|string|false|none|none|
|Tax|string|false|none|none|
|TaxCurrency|string|false|none|none|
|TranControlNbr|string|false|none|none|
|TranPlatingNbr|string|false|none|none|

<h2 id="tocS_Air">Air</h2>
<!-- backwards compatibility -->
<a id="schemaair"></a>
<a id="schema_Air"></a>
<a id="tocSair"></a>
<a id="tocsair"></a>

```json
{
  "AircraftCode": "string",
  "Bags": "string",
  "Cabin": "string",
  "CancellationNumber": "string",
  "CancellationPolicy": "string",
  "CarbonEmissionLbs": 0,
  "CarbonModel": 0,
  "Charges": {
    "Fixed": [
      {
        "Amount": 0,
        "Currency": "string",
        "Description": "string",
        "IsPaid": true,
        "IsPrimary": true,
        "SemanticsCode": "string",
        "SemanticsVendorType": "string",
        "StartDateLocal": "string",
        "Vendor": "string",
        "VendorChargeCode": "string"
      }
    ],
    "Percent": [
      {
        "Amount": 0,
        "Currency": "string",
        "Description": "string",
        "IsPaid": true,
        "IsPrimary": true,
        "SemanticsCode": "string",
        "SemanticsVendorType": "string",
        "StartDateLocal": "string",
        "Vendor": "string",
        "VendorChargeCode": "string"
      }
    ],
    "Rate": [
      {
        "Amount": 0,
        "Currency": "string",
        "Description": "string",
        "IsPaid": true,
        "IsPrimary": true,
        "NumUnits": 0,
        "PerUnit": "string",
        "SemanticsCode": "string",
        "SemanticsVendorType": "string",
        "StartDateLocal": "string",
        "Vendor": "string",
        "VendorChargeCode": "string"
      }
    ],
    "RateWithAllowance": [
      {
        "AllowanceAmount": 0,
        "AllowanceIsUnlimited": true,
        "AllowanceNumUnits": 0,
        "AllowanceUnit": "string",
        "Amount": 0,
        "Currency": "string",
        "Description": "string",
        "IsPaid": true,
        "IsPrimary": true,
        "NumUnits": 0,
        "PerUnit": "string",
        "SemanticsCode": "string",
        "SemanticsVendorType": "string",
        "StartDateLocal": "string",
        "Vendor": "string",
        "VendorChargeCode": "string"
      }
    ]
  },
  "CheckedBaggage": "string",
  "ClassOfService": "string",
  "ConfirmationNumber": "string",
  "DateCancelledUtc": "string",
  "DateCreatedUtc": "string",
  "DateModifiedUtc": "string",
  "Duration": 0,
  "ETicket": "string",
  "EndCityCode": "string",
  "EndDateLocal": "string",
  "EndDateUtc": "string",
  "EndGate": "string",
  "EndTerminal": "string",
  "FlightNumber": "string",
  "FrequentTravelerId": "string",
  "IsOpenSegment": true,
  "IsPreferredVendor": 0,
  "IsUpgradeAllowed": true,
  "LegId": 0,
  "Meals": "string",
  "Miles": 0,
  "Notes": "string",
  "NumStops": 0,
  "OpenSegment": "string",
  "OperatedByFlightNumber": "string",
  "OperatedByVendor": "string",
  "OperatedByVendorName": "string",
  "Remarks": {
    "TripLinkRemarks": [
      {
        "TripLinkRemark": [
          {
            "Text": "string"
          }
        ]
      }
    ]
  },
  "RuleViolations": [
    {
      "CompanyReasonCode": "string",
      "CompanyRuleText": "string",
      "ViolationReasonCode": 0
    }
  ],
  "Seats": [
    {
      "PassengerRph": 0,
      "SeatNumber": "string",
      "Status": "string"
    }
  ],
  "Services": "string",
  "SpecialInstructions": "string",
  "StartCityCode": "string",
  "StartDateLocal": "string",
  "StartDateUtc": "string",
  "StartGate": "string",
  "StartTerminal": "string",
  "Status": "string",
  "TimeZone": "string",
  "TimeZoneId": 0,
  "UpgradedDateTime": "string",
  "Vendor": "string",
  "VendorFlags": "string",
  "VendorName": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|AircraftCode|string|false|none|none|
|Bags|string|false|none|none|
|Cabin|string|false|none|none|
|CancellationNumber|string|false|none|none|
|CancellationPolicy|string|false|none|none|
|CarbonEmissionLbs|number|false|none|none|
|CarbonModel|integer|false|none|none|
|Charges|[ChargeDetail](#schemachargedetail)|false|none|none|
|CheckedBaggage|string|false|none|none|
|ClassOfService|string|false|none|none|
|ConfirmationNumber|string|false|none|none|
|DateCancelledUtc|string|false|none|none|
|DateCreatedUtc|string|false|none|none|
|DateModifiedUtc|string|false|none|none|
|Duration|integer|false|none|none|
|ETicket|string|false|none|none|
|EndCityCode|string|false|none|none|
|EndDateLocal|string|false|none|none|
|EndDateUtc|string|false|none|none|
|EndGate|string|false|none|none|
|EndTerminal|string|false|none|none|
|FlightNumber|string|false|none|none|
|FrequentTravelerId|string|false|none|none|
|IsOpenSegment|boolean|false|none|none|
|IsPreferredVendor|integer|false|none|none|
|IsUpgradeAllowed|boolean|false|none|none|
|LegId|integer|false|none|none|
|Meals|string|false|none|none|
|Miles|integer|false|none|none|
|Notes|string|false|none|none|
|NumStops|integer|false|none|none|
|OpenSegment|string|false|none|none|
|OperatedByFlightNumber|string|false|none|none|
|OperatedByVendor|string|false|none|none|
|OperatedByVendorName|string|false|none|none|
|Remarks|[Remarks](#schemaremarks)|false|none|none|
|RuleViolations|[[RuleViolation](#schemaruleviolation)]|false|none|none|
|Seats|[[AirSeat](#schemaairseat)]|false|none|none|
|Services|string|false|none|none|
|SpecialInstructions|string|false|none|none|
|StartCityCode|string|false|none|none|
|StartDateLocal|string|false|none|none|
|StartDateUtc|string|false|none|none|
|StartGate|string|false|none|none|
|StartTerminal|string|false|none|none|
|Status|string|false|none|none|
|TimeZone|string|false|none|none|
|TimeZoneId|integer|false|none|none|
|UpgradedDateTime|string|false|none|none|
|Vendor|string|false|none|none|
|VendorFlags|string|false|none|none|
|VendorName|string|false|none|none|

<h2 id="tocS_AirSeat">AirSeat</h2>
<!-- backwards compatibility -->
<a id="schemaairseat"></a>
<a id="schema_AirSeat"></a>
<a id="tocSairseat"></a>
<a id="tocsairseat"></a>

```json
{
  "PassengerRph": 0,
  "SeatNumber": "string",
  "Status": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|PassengerRph|integer|false|none|none|
|SeatNumber|string|false|none|none|
|Status|string|false|none|none|

<h2 id="tocS_AirlineAdjustment">AirlineAdjustment</h2>
<!-- backwards compatibility -->
<a id="schemaairlineadjustment"></a>
<a id="schema_AirlineAdjustment"></a>
<a id="tocSairlineadjustment"></a>
<a id="tocsairlineadjustment"></a>

```json
{
  "AddCollectAmount": 0,
  "AdjustmentDateTime": "string",
  "AdjustmentDateTimeUTC": "string",
  "AdjustmentType": "string",
  "AirlineCharges": {
    "Fixed": [
      {
        "Amount": 0,
        "Currency": "string",
        "Description": "string",
        "IsPaid": true,
        "IsPrimary": true,
        "SemanticsCode": "string",
        "SemanticsVendorType": "string",
        "StartDateLocal": "string",
        "Vendor": "string",
        "VendorChargeCode": "string"
      }
    ],
    "Percent": [
      {
        "Amount": 0,
        "Currency": "string",
        "Description": "string",
        "IsPaid": true,
        "IsPrimary": true,
        "SemanticsCode": "string",
        "SemanticsVendorType": "string",
        "StartDateLocal": "string",
        "Vendor": "string",
        "VendorChargeCode": "string"
      }
    ],
    "Rate": [
      {
        "Amount": 0,
        "Currency": "string",
        "Description": "string",
        "IsPaid": true,
        "IsPrimary": true,
        "NumUnits": 0,
        "PerUnit": "string",
        "SemanticsCode": "string",
        "SemanticsVendorType": "string",
        "StartDateLocal": "string",
        "Vendor": "string",
        "VendorChargeCode": "string"
      }
    ],
    "RateWithAllowance": [
      {
        "AllowanceAmount": 0,
        "AllowanceIsUnlimited": true,
        "AllowanceNumUnits": 0,
        "AllowanceUnit": "string",
        "Amount": 0,
        "Currency": "string",
        "Description": "string",
        "IsPaid": true,
        "IsPrimary": true,
        "NumUnits": 0,
        "PerUnit": "string",
        "SemanticsCode": "string",
        "SemanticsVendorType": "string",
        "StartDateLocal": "string",
        "Vendor": "string",
        "VendorChargeCode": "string"
      }
    ]
  },
  "DateCreatedUtc": "string",
  "DateModifiedUtc": "string",
  "PassengerName": "string",
  "PlatingCarrierNumericCode": "string",
  "PlatingControlNumber": "string",
  "RecordLocator": "string",
  "Taxes": [
    {
      "TaxAmount": 0,
      "TaxAuthority": "string",
      "TaxName": "string",
      "TaxRate": 0,
      "TaxType": "string"
    }
  ],
  "TotalAdjustment": 0,
  "TotalAdjustmentCurrency": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|AddCollectAmount|number|false|none|none|
|AdjustmentDateTime|string|false|none|none|
|AdjustmentDateTimeUTC|string|false|none|none|
|AdjustmentType|string|false|none|none|
|AirlineCharges|[ChargeDetail](#schemachargedetail)|false|none|none|
|DateCreatedUtc|string|false|none|none|
|DateModifiedUtc|string|false|none|none|
|PassengerName|string|false|none|none|
|PlatingCarrierNumericCode|string|false|none|none|
|PlatingControlNumber|string|false|none|none|
|RecordLocator|string|false|none|none|
|Taxes|[[Tax](#schematax)]|false|none|none|
|TotalAdjustment|number|false|none|none|
|TotalAdjustmentCurrency|string|false|none|none|

<h2 id="tocS_AirlineTicket">AirlineTicket</h2>
<!-- backwards compatibility -->
<a id="schemaairlineticket"></a>
<a id="schema_AirlineTicket"></a>
<a id="tocSairlineticket"></a>
<a id="tocsairlineticket"></a>

```json
{
  "AccountingLine": {
    "AirlineCode": "string",
    "AmountPaid": "string",
    "AmountPaidCurrency": "string",
    "CCNumber": "string",
    "Comment": "string",
    "Commission": "string",
    "CommissionCurrency": "string",
    "ExchangedTicketNumber": "string",
    "FOPMethod": "string",
    "Fare": "string",
    "FareCurrency": "string",
    "IssueDate": "string",
    "MCOType": "string",
    "Tax": "string",
    "TaxCurrency": "string",
    "TranControlNbr": "string",
    "TranPlatingNbr": "string"
  },
  "AddCollectAmount": 0,
  "AirlineCharges": {
    "Fixed": [
      {
        "Amount": 0,
        "Currency": "string",
        "Description": "string",
        "IsPaid": true,
        "IsPrimary": true,
        "SemanticsCode": "string",
        "SemanticsVendorType": "string",
        "StartDateLocal": "string",
        "Vendor": "string",
        "VendorChargeCode": "string"
      }
    ],
    "Percent": [
      {
        "Amount": 0,
        "Currency": "string",
        "Description": "string",
        "IsPaid": true,
        "IsPrimary": true,
        "SemanticsCode": "string",
        "SemanticsVendorType": "string",
        "StartDateLocal": "string",
        "Vendor": "string",
        "VendorChargeCode": "string"
      }
    ],
    "Rate": [
      {
        "Amount": 0,
        "Currency": "string",
        "Description": "string",
        "IsPaid": true,
        "IsPrimary": true,
        "NumUnits": 0,
        "PerUnit": "string",
        "SemanticsCode": "string",
        "SemanticsVendorType": "string",
        "StartDateLocal": "string",
        "Vendor": "string",
        "VendorChargeCode": "string"
      }
    ],
    "RateWithAllowance": [
      {
        "AllowanceAmount": 0,
        "AllowanceIsUnlimited": true,
        "AllowanceNumUnits": 0,
        "AllowanceUnit": "string",
        "Amount": 0,
        "Currency": "string",
        "Description": "string",
        "IsPaid": true,
        "IsPrimary": true,
        "NumUnits": 0,
        "PerUnit": "string",
        "SemanticsCode": "string",
        "SemanticsVendorType": "string",
        "StartDateLocal": "string",
        "Vendor": "string",
        "VendorChargeCode": "string"
      }
    ]
  },
  "AirlineTicketCoupons": [
    {
      "ClassOfService": "string",
      "CouponNumber": 0,
      "CouponStatus": "string",
      "EndCityCode": "string",
      "FlightNumber": "string",
      "NotValidAfterDate": "string",
      "NotValidBeforeDate": "string",
      "RateCode": "string",
      "StartCityCode": "string",
      "StartDateLocal": "string",
      "Status": "string",
      "TicketDesignator": "string",
      "Vendor": "string"
    }
  ],
  "AirlineTicketExchanges": [
    {
      "Amount": 0,
      "AppliedSegment1": 0,
      "AppliedSegment10": 0,
      "AppliedSegment2": 0,
      "AppliedSegment3": 0,
      "AppliedSegment4": 0,
      "AppliedSegment5": 0,
      "AppliedSegment6": 0,
      "AppliedSegment7": 0,
      "AppliedSegment8": 0,
      "AppliedSegment9": 0,
      "Currency": "string",
      "DateModifiedUtc": "string",
      "OldRecordLocator": "string",
      "PlatingCarrierNumericCode": "string",
      "PlatingControlNumber": "string"
    }
  ],
  "AirlineTicketFareBreakups": [
    {
      "BaseFare": 0,
      "ClassOfService": "string",
      "Currency": "string",
      "EndCityCode": "string",
      "IsRefundable": true,
      "StartCityCode": "string",
      "TotalFare": 0,
      "Vendor": "string"
    }
  ],
  "BaseFare": 0,
  "BaseFareCurrency": "string",
  "BaseFareNuc": 0,
  "BaseFareNucCurrency": "string",
  "ComparisonFare": 0,
  "ComparisonFareCurrency": "string",
  "DateCreatedUtc": "string",
  "DateModifiedUtc": "string",
  "Endorsements": "string",
  "InvoiceNumber": "string",
  "IssueDateTime": "string",
  "IssueDateTimeUTC": "string",
  "IssuingIataAgencyNumber": 0,
  "IssuingPseudoCity": "string",
  "LinearFareConstructor": "string",
  "MasterTicketNumber": "string",
  "NameReference": "string",
  "PassengerName": "string",
  "PlatingCarrierNumericCode": "string",
  "PlatingControlNumber": "string",
  "ProgramCarrierCode": "string",
  "ProgramMembershipNumber": "string",
  "RecordLocator": "string",
  "SabreDkNumber": "string",
  "Taxes": [
    {
      "TaxAmount": 0,
      "TaxAuthority": "string",
      "TaxName": "string",
      "TaxRate": 0,
      "TaxType": "string"
    }
  ],
  "TicketType": "string",
  "Ticketless": true,
  "TotalFare": 0,
  "TotalFareCurrency": "string",
  "TourIdentifier": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|AccountingLine|[AccountingLine](#schemaaccountingline)|false|none|none|
|AddCollectAmount|number|false|none|none|
|AirlineCharges|[ChargeDetail](#schemachargedetail)|false|none|none|
|AirlineTicketCoupons|[[AirlineTicketCoupon](#schemaairlineticketcoupon)]|false|none|none|
|AirlineTicketExchanges|[[AirlineTicketExchange](#schemaairlineticketexchange)]|false|none|none|
|AirlineTicketFareBreakups|[[AirlineTicketFareBreakup](#schemaairlineticketfarebreakup)]|false|none|none|
|BaseFare|number|false|none|none|
|BaseFareCurrency|string|false|none|none|
|BaseFareNuc|number|false|none|none|
|BaseFareNucCurrency|string|false|none|none|
|ComparisonFare|number|false|none|none|
|ComparisonFareCurrency|string|false|none|none|
|DateCreatedUtc|string|false|none|none|
|DateModifiedUtc|string|false|none|none|
|Endorsements|string|false|none|none|
|InvoiceNumber|string|false|none|none|
|IssueDateTime|string|false|none|none|
|IssueDateTimeUTC|string|false|none|none|
|IssuingIataAgencyNumber|integer|false|none|none|
|IssuingPseudoCity|string|false|none|none|
|LinearFareConstructor|string|false|none|none|
|MasterTicketNumber|string|false|none|none|
|NameReference|string|false|none|none|
|PassengerName|string|false|none|none|
|PlatingCarrierNumericCode|string|false|none|none|
|PlatingControlNumber|string|false|none|none|
|ProgramCarrierCode|string|false|none|none|
|ProgramMembershipNumber|string|false|none|none|
|RecordLocator|string|false|none|none|
|SabreDkNumber|string|false|none|none|
|Taxes|[[Tax](#schematax)]|false|none|none|
|TicketType|string|false|none|none|
|Ticketless|boolean|false|none|none|
|TotalFare|number|false|none|none|
|TotalFareCurrency|string|false|none|none|
|TourIdentifier|string|false|none|none|

<h2 id="tocS_AirlineTicketCoupon">AirlineTicketCoupon</h2>
<!-- backwards compatibility -->
<a id="schemaairlineticketcoupon"></a>
<a id="schema_AirlineTicketCoupon"></a>
<a id="tocSairlineticketcoupon"></a>
<a id="tocsairlineticketcoupon"></a>

```json
{
  "ClassOfService": "string",
  "CouponNumber": 0,
  "CouponStatus": "string",
  "EndCityCode": "string",
  "FlightNumber": "string",
  "NotValidAfterDate": "string",
  "NotValidBeforeDate": "string",
  "RateCode": "string",
  "StartCityCode": "string",
  "StartDateLocal": "string",
  "Status": "string",
  "TicketDesignator": "string",
  "Vendor": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|ClassOfService|string|false|none|none|
|CouponNumber|integer|false|none|none|
|CouponStatus|string|false|none|none|
|EndCityCode|string|false|none|none|
|FlightNumber|string|false|none|none|
|NotValidAfterDate|string|false|none|none|
|NotValidBeforeDate|string|false|none|none|
|RateCode|string|false|none|none|
|StartCityCode|string|false|none|none|
|StartDateLocal|string|false|none|none|
|Status|string|false|none|none|
|TicketDesignator|string|false|none|none|
|Vendor|string|false|none|none|

<h2 id="tocS_AirlineTicketExchange">AirlineTicketExchange</h2>
<!-- backwards compatibility -->
<a id="schemaairlineticketexchange"></a>
<a id="schema_AirlineTicketExchange"></a>
<a id="tocSairlineticketexchange"></a>
<a id="tocsairlineticketexchange"></a>

```json
{
  "Amount": 0,
  "AppliedSegment1": 0,
  "AppliedSegment10": 0,
  "AppliedSegment2": 0,
  "AppliedSegment3": 0,
  "AppliedSegment4": 0,
  "AppliedSegment5": 0,
  "AppliedSegment6": 0,
  "AppliedSegment7": 0,
  "AppliedSegment8": 0,
  "AppliedSegment9": 0,
  "Currency": "string",
  "DateModifiedUtc": "string",
  "OldRecordLocator": "string",
  "PlatingCarrierNumericCode": "string",
  "PlatingControlNumber": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Amount|number|false|none|none|
|AppliedSegment1|integer|false|none|none|
|AppliedSegment10|integer|false|none|none|
|AppliedSegment2|integer|false|none|none|
|AppliedSegment3|integer|false|none|none|
|AppliedSegment4|integer|false|none|none|
|AppliedSegment5|integer|false|none|none|
|AppliedSegment6|integer|false|none|none|
|AppliedSegment7|integer|false|none|none|
|AppliedSegment8|integer|false|none|none|
|AppliedSegment9|integer|false|none|none|
|Currency|string|false|none|none|
|DateModifiedUtc|string|false|none|none|
|OldRecordLocator|string|false|none|none|
|PlatingCarrierNumericCode|string|false|none|none|
|PlatingControlNumber|string|false|none|none|

<h2 id="tocS_AirlineTicketFareBreakup">AirlineTicketFareBreakup</h2>
<!-- backwards compatibility -->
<a id="schemaairlineticketfarebreakup"></a>
<a id="schema_AirlineTicketFareBreakup"></a>
<a id="tocSairlineticketfarebreakup"></a>
<a id="tocsairlineticketfarebreakup"></a>

```json
{
  "BaseFare": 0,
  "ClassOfService": "string",
  "Currency": "string",
  "EndCityCode": "string",
  "IsRefundable": true,
  "StartCityCode": "string",
  "TotalFare": 0,
  "Vendor": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|BaseFare|number|false|none|none|
|ClassOfService|string|false|none|none|
|Currency|string|false|none|none|
|EndCityCode|string|false|none|none|
|IsRefundable|boolean|false|none|none|
|StartCityCode|string|false|none|none|
|TotalFare|number|false|none|none|
|Vendor|string|false|none|none|

<h2 id="tocS_BaseAirlineTicket">BaseAirlineTicket</h2>
<!-- backwards compatibility -->
<a id="schemabaseairlineticket"></a>
<a id="schema_BaseAirlineTicket"></a>
<a id="tocSbaseairlineticket"></a>
<a id="tocsbaseairlineticket"></a>

```json
{
  "AirlineAdjustment": [
    {
      "AddCollectAmount": 0,
      "AdjustmentDateTime": "string",
      "AdjustmentDateTimeUTC": "string",
      "AdjustmentType": "string",
      "AirlineCharges": {
        "Fixed": [
          {
            "Amount": 0,
            "Currency": "string",
            "Description": "string",
            "IsPaid": true,
            "IsPrimary": true,
            "SemanticsCode": "string",
            "SemanticsVendorType": "string",
            "StartDateLocal": "string",
            "Vendor": "string",
            "VendorChargeCode": "string"
          }
        ],
        "Percent": [
          {
            "Amount": 0,
            "Currency": "string",
            "Description": "string",
            "IsPaid": true,
            "IsPrimary": true,
            "SemanticsCode": "string",
            "SemanticsVendorType": "string",
            "StartDateLocal": "string",
            "Vendor": "string",
            "VendorChargeCode": "string"
          }
        ],
        "Rate": [
          {
            "Amount": 0,
            "Currency": "string",
            "Description": "string",
            "IsPaid": true,
            "IsPrimary": true,
            "NumUnits": 0,
            "PerUnit": "string",
            "SemanticsCode": "string",
            "SemanticsVendorType": "string",
            "StartDateLocal": "string",
            "Vendor": "string",
            "VendorChargeCode": "string"
          }
        ],
        "RateWithAllowance": [
          {
            "AllowanceAmount": 0,
            "AllowanceIsUnlimited": true,
            "AllowanceNumUnits": 0,
            "AllowanceUnit": "string",
            "Amount": 0,
            "Currency": "string",
            "Description": "string",
            "IsPaid": true,
            "IsPrimary": true,
            "NumUnits": 0,
            "PerUnit": "string",
            "SemanticsCode": "string",
            "SemanticsVendorType": "string",
            "StartDateLocal": "string",
            "Vendor": "string",
            "VendorChargeCode": "string"
          }
        ]
      },
      "DateCreatedUtc": "string",
      "DateModifiedUtc": "string",
      "PassengerName": "string",
      "PlatingCarrierNumericCode": "string",
      "PlatingControlNumber": "string",
      "RecordLocator": "string",
      "Taxes": [
        {
          "TaxAmount": 0,
          "TaxAuthority": "string",
          "TaxName": "string",
          "TaxRate": 0,
          "TaxType": "string"
        }
      ],
      "TotalAdjustment": 0,
      "TotalAdjustmentCurrency": "string"
    }
  ],
  "AirlineTicket": [
    {
      "AccountingLine": {
        "AirlineCode": "string",
        "AmountPaid": "string",
        "AmountPaidCurrency": "string",
        "CCNumber": "string",
        "Comment": "string",
        "Commission": "string",
        "CommissionCurrency": "string",
        "ExchangedTicketNumber": "string",
        "FOPMethod": "string",
        "Fare": "string",
        "FareCurrency": "string",
        "IssueDate": "string",
        "MCOType": "string",
        "Tax": "string",
        "TaxCurrency": "string",
        "TranControlNbr": "string",
        "TranPlatingNbr": "string"
      },
      "AddCollectAmount": 0,
      "AirlineCharges": {
        "Fixed": [
          {
            "Amount": 0,
            "Currency": "string",
            "Description": "string",
            "IsPaid": true,
            "IsPrimary": true,
            "SemanticsCode": "string",
            "SemanticsVendorType": "string",
            "StartDateLocal": "string",
            "Vendor": "string",
            "VendorChargeCode": "string"
          }
        ],
        "Percent": [
          {
            "Amount": 0,
            "Currency": "string",
            "Description": "string",
            "IsPaid": true,
            "IsPrimary": true,
            "SemanticsCode": "string",
            "SemanticsVendorType": "string",
            "StartDateLocal": "string",
            "Vendor": "string",
            "VendorChargeCode": "string"
          }
        ],
        "Rate": [
          {
            "Amount": 0,
            "Currency": "string",
            "Description": "string",
            "IsPaid": true,
            "IsPrimary": true,
            "NumUnits": 0,
            "PerUnit": "string",
            "SemanticsCode": "string",
            "SemanticsVendorType": "string",
            "StartDateLocal": "string",
            "Vendor": "string",
            "VendorChargeCode": "string"
          }
        ],
        "RateWithAllowance": [
          {
            "AllowanceAmount": 0,
            "AllowanceIsUnlimited": true,
            "AllowanceNumUnits": 0,
            "AllowanceUnit": "string",
            "Amount": 0,
            "Currency": "string",
            "Description": "string",
            "IsPaid": true,
            "IsPrimary": true,
            "NumUnits": 0,
            "PerUnit": "string",
            "SemanticsCode": "string",
            "SemanticsVendorType": "string",
            "StartDateLocal": "string",
            "Vendor": "string",
            "VendorChargeCode": "string"
          }
        ]
      },
      "AirlineTicketCoupons": [
        {
          "ClassOfService": "string",
          "CouponNumber": 0,
          "CouponStatus": "string",
          "EndCityCode": "string",
          "FlightNumber": "string",
          "NotValidAfterDate": "string",
          "NotValidBeforeDate": "string",
          "RateCode": "string",
          "StartCityCode": "string",
          "StartDateLocal": "string",
          "Status": "string",
          "TicketDesignator": "string",
          "Vendor": "string"
        }
      ],
      "AirlineTicketExchanges": [
        {
          "Amount": 0,
          "AppliedSegment1": 0,
          "AppliedSegment10": 0,
          "AppliedSegment2": 0,
          "AppliedSegment3": 0,
          "AppliedSegment4": 0,
          "AppliedSegment5": 0,
          "AppliedSegment6": 0,
          "AppliedSegment7": 0,
          "AppliedSegment8": 0,
          "AppliedSegment9": 0,
          "Currency": "string",
          "DateModifiedUtc": "string",
          "OldRecordLocator": "string",
          "PlatingCarrierNumericCode": "string",
          "PlatingControlNumber": "string"
        }
      ],
      "AirlineTicketFareBreakups": [
        {
          "BaseFare": 0,
          "ClassOfService": "string",
          "Currency": "string",
          "EndCityCode": "string",
          "IsRefundable": true,
          "StartCityCode": "string",
          "TotalFare": 0,
          "Vendor": "string"
        }
      ],
      "BaseFare": 0,
      "BaseFareCurrency": "string",
      "BaseFareNuc": 0,
      "BaseFareNucCurrency": "string",
      "ComparisonFare": 0,
      "ComparisonFareCurrency": "string",
      "DateCreatedUtc": "string",
      "DateModifiedUtc": "string",
      "Endorsements": "string",
      "InvoiceNumber": "string",
      "IssueDateTime": "string",
      "IssueDateTimeUTC": "string",
      "IssuingIataAgencyNumber": 0,
      "IssuingPseudoCity": "string",
      "LinearFareConstructor": "string",
      "MasterTicketNumber": "string",
      "NameReference": "string",
      "PassengerName": "string",
      "PlatingCarrierNumericCode": "string",
      "PlatingControlNumber": "string",
      "ProgramCarrierCode": "string",
      "ProgramMembershipNumber": "string",
      "RecordLocator": "string",
      "SabreDkNumber": "string",
      "Taxes": [
        {
          "TaxAmount": 0,
          "TaxAuthority": "string",
          "TaxName": "string",
          "TaxRate": 0,
          "TaxType": "string"
        }
      ],
      "TicketType": "string",
      "Ticketless": true,
      "TotalFare": 0,
      "TotalFareCurrency": "string",
      "TourIdentifier": "string"
    }
  ],
  "ManualAirlineTicket": [
    {
      "AirlineCharges": {
        "Fixed": [
          {
            "Amount": 0,
            "Currency": "string",
            "Description": "string",
            "IsPaid": true,
            "IsPrimary": true,
            "SemanticsCode": "string",
            "SemanticsVendorType": "string",
            "StartDateLocal": "string",
            "Vendor": "string",
            "VendorChargeCode": "string"
          }
        ],
        "Percent": [
          {
            "Amount": 0,
            "Currency": "string",
            "Description": "string",
            "IsPaid": true,
            "IsPrimary": true,
            "SemanticsCode": "string",
            "SemanticsVendorType": "string",
            "StartDateLocal": "string",
            "Vendor": "string",
            "VendorChargeCode": "string"
          }
        ],
        "Rate": [
          {
            "Amount": 0,
            "Currency": "string",
            "Description": "string",
            "IsPaid": true,
            "IsPrimary": true,
            "NumUnits": 0,
            "PerUnit": "string",
            "SemanticsCode": "string",
            "SemanticsVendorType": "string",
            "StartDateLocal": "string",
            "Vendor": "string",
            "VendorChargeCode": "string"
          }
        ],
        "RateWithAllowance": [
          {
            "AllowanceAmount": 0,
            "AllowanceIsUnlimited": true,
            "AllowanceNumUnits": 0,
            "AllowanceUnit": "string",
            "Amount": 0,
            "Currency": "string",
            "Description": "string",
            "IsPaid": true,
            "IsPrimary": true,
            "NumUnits": 0,
            "PerUnit": "string",
            "SemanticsCode": "string",
            "SemanticsVendorType": "string",
            "StartDateLocal": "string",
            "Vendor": "string",
            "VendorChargeCode": "string"
          }
        ]
      },
      "BaseFare": 0,
      "BaseFareCurrency": "string",
      "DateCreatedUtc": "string",
      "DateModifiedUtc": "string",
      "Taxes": [
        {
          "TaxAmount": 0,
          "TaxAuthority": "string",
          "TaxName": "string",
          "TaxRate": 0,
          "TaxType": "string"
        }
      ],
      "TotalFare": 0,
      "TotalFareCurrency": "string"
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|AirlineAdjustment|[[AirlineAdjustment](#schemaairlineadjustment)]|false|none|none|
|AirlineTicket|[[AirlineTicket](#schemaairlineticket)]|false|none|none|
|ManualAirlineTicket|[[ManualAirlineTicket](#schemamanualairlineticket)]|false|none|none|

<h2 id="tocS_BaseRailPayment">BaseRailPayment</h2>
<!-- backwards compatibility -->
<a id="schemabaserailpayment"></a>
<a id="schema_BaseRailPayment"></a>
<a id="tocSbaserailpayment"></a>
<a id="tocsbaserailpayment"></a>

```json
{
  "RailAdjustment": [
    {
      "AdjustmentDateTime": "string",
      "AdjustmentDateTimeUTC": "string",
      "AdjustmentType": "string",
      "DateCreatedUtc": "string",
      "DateModifiedUtc": "string",
      "RailCharges": {
        "Fixed": [
          {
            "Amount": 0,
            "Currency": "string",
            "Description": "string",
            "IsPaid": true,
            "IsPrimary": true,
            "SemanticsCode": "string",
            "SemanticsVendorType": "string",
            "StartDateLocal": "string",
            "Vendor": "string",
            "VendorChargeCode": "string"
          }
        ],
        "Percent": [
          {
            "Amount": 0,
            "Currency": "string",
            "Description": "string",
            "IsPaid": true,
            "IsPrimary": true,
            "SemanticsCode": "string",
            "SemanticsVendorType": "string",
            "StartDateLocal": "string",
            "Vendor": "string",
            "VendorChargeCode": "string"
          }
        ],
        "Rate": [
          {
            "Amount": 0,
            "Currency": "string",
            "Description": "string",
            "IsPaid": true,
            "IsPrimary": true,
            "NumUnits": 0,
            "PerUnit": "string",
            "SemanticsCode": "string",
            "SemanticsVendorType": "string",
            "StartDateLocal": "string",
            "Vendor": "string",
            "VendorChargeCode": "string"
          }
        ],
        "RateWithAllowance": [
          {
            "AllowanceAmount": 0,
            "AllowanceIsUnlimited": true,
            "AllowanceNumUnits": 0,
            "AllowanceUnit": "string",
            "Amount": 0,
            "Currency": "string",
            "Description": "string",
            "IsPaid": true,
            "IsPrimary": true,
            "NumUnits": 0,
            "PerUnit": "string",
            "SemanticsCode": "string",
            "SemanticsVendorType": "string",
            "StartDateLocal": "string",
            "Vendor": "string",
            "VendorChargeCode": "string"
          }
        ]
      },
      "Taxes": [
        {
          "TaxAmount": 0,
          "TaxAuthority": "string",
          "TaxName": "string",
          "TaxRate": 0,
          "TaxType": "string"
        }
      ],
      "TicketDocumentIdentifier": "string",
      "TotalAdjustment": 0,
      "TotalAdjustmentCurrency": "string"
    }
  ],
  "RailPayment": [
    {
      "BaseFare": 0,
      "BaseFareCurrency": "string",
      "DateCreatedUtc": "string",
      "DateModifiedUtc": "string",
      "IncludesVAT": true,
      "IssueByDate": "string",
      "IssueDateTime": "string",
      "IssueDateTimeUTC": "string",
      "RailCharges": {
        "Fixed": [
          {
            "Amount": 0,
            "Currency": "string",
            "Description": "string",
            "IsPaid": true,
            "IsPrimary": true,
            "SemanticsCode": "string",
            "SemanticsVendorType": "string",
            "StartDateLocal": "string",
            "Vendor": "string",
            "VendorChargeCode": "string"
          }
        ],
        "Percent": [
          {
            "Amount": 0,
            "Currency": "string",
            "Description": "string",
            "IsPaid": true,
            "IsPrimary": true,
            "SemanticsCode": "string",
            "SemanticsVendorType": "string",
            "StartDateLocal": "string",
            "Vendor": "string",
            "VendorChargeCode": "string"
          }
        ],
        "Rate": [
          {
            "Amount": 0,
            "Currency": "string",
            "Description": "string",
            "IsPaid": true,
            "IsPrimary": true,
            "NumUnits": 0,
            "PerUnit": "string",
            "SemanticsCode": "string",
            "SemanticsVendorType": "string",
            "StartDateLocal": "string",
            "Vendor": "string",
            "VendorChargeCode": "string"
          }
        ],
        "RateWithAllowance": [
          {
            "AllowanceAmount": 0,
            "AllowanceIsUnlimited": true,
            "AllowanceNumUnits": 0,
            "AllowanceUnit": "string",
            "Amount": 0,
            "Currency": "string",
            "Description": "string",
            "IsPaid": true,
            "IsPrimary": true,
            "NumUnits": 0,
            "PerUnit": "string",
            "SemanticsCode": "string",
            "SemanticsVendorType": "string",
            "StartDateLocal": "string",
            "Vendor": "string",
            "VendorChargeCode": "string"
          }
        ]
      },
      "TaxInvoice": true,
      "Taxes": [
        {
          "TaxAmount": 0,
          "TaxAuthority": "string",
          "TaxName": "string",
          "TaxRate": 0,
          "TaxType": "string"
        }
      ],
      "TicketDocumentIdentifier": "string",
      "TicketType": "string",
      "TotalFare": 0,
      "TotalFareCurrency": "string",
      "vatApplicable": true
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|RailAdjustment|[[RailAdjustment](#schemarailadjustment)]|false|none|none|
|RailPayment|[[RailPayment](#schemarailpayment)]|false|none|none|

<h2 id="tocS_Booking">Booking</h2>
<!-- backwards compatibility -->
<a id="schemabooking"></a>
<a id="schema_Booking"></a>
<a id="tocSbooking"></a>
<a id="tocsbooking"></a>

```json
{
  "AgencyName": "string",
  "AgencyPCC": "string",
  "AirfareQuotes": [
    {
      "AirlineCharges": {
        "Fixed": [
          {
            "Amount": 0,
            "Currency": "string",
            "Description": "string",
            "IsPaid": true,
            "IsPrimary": true,
            "SemanticsCode": "string",
            "SemanticsVendorType": "string",
            "StartDateLocal": "string",
            "Vendor": "string",
            "VendorChargeCode": "string"
          }
        ],
        "Percent": [
          {
            "Amount": 0,
            "Currency": "string",
            "Description": "string",
            "IsPaid": true,
            "IsPrimary": true,
            "SemanticsCode": "string",
            "SemanticsVendorType": "string",
            "StartDateLocal": "string",
            "Vendor": "string",
            "VendorChargeCode": "string"
          }
        ],
        "Rate": [
          {
            "Amount": 0,
            "Currency": "string",
            "Description": "string",
            "IsPaid": true,
            "IsPrimary": true,
            "NumUnits": 0,
            "PerUnit": "string",
            "SemanticsCode": "string",
            "SemanticsVendorType": "string",
            "StartDateLocal": "string",
            "Vendor": "string",
            "VendorChargeCode": "string"
          }
        ],
        "RateWithAllowance": [
          {
            "AllowanceAmount": 0,
            "AllowanceIsUnlimited": true,
            "AllowanceNumUnits": 0,
            "AllowanceUnit": "string",
            "Amount": 0,
            "Currency": "string",
            "Description": "string",
            "IsPaid": true,
            "IsPrimary": true,
            "NumUnits": 0,
            "PerUnit": "string",
            "SemanticsCode": "string",
            "SemanticsVendorType": "string",
            "StartDateLocal": "string",
            "Vendor": "string",
            "VendorChargeCode": "string"
          }
        ]
      },
      "BaseFare": 0,
      "BaseFareCurrency": "string",
      "BaseFareNuc": 0,
      "BaseFareNucCurrency": "string",
      "DateCreatedUtc": "string",
      "DateModifiedUtc": "string",
      "Endorsements": "string",
      "IssueByDate": "string",
      "TotalFare": 0,
      "TotalFareCurrency": "string"
    }
  ],
  "AirlineTickets": {
    "AirlineAdjustment": [
      {
        "AddCollectAmount": 0,
        "AdjustmentDateTime": "string",
        "AdjustmentDateTimeUTC": "string",
        "AdjustmentType": "string",
        "AirlineCharges": {
          "Fixed": [
            {
              "Amount": 0,
              "Currency": "string",
              "Description": "string",
              "IsPaid": true,
              "IsPrimary": true,
              "SemanticsCode": "string",
              "SemanticsVendorType": "string",
              "StartDateLocal": "string",
              "Vendor": "string",
              "VendorChargeCode": "string"
            }
          ],
          "Percent": [
            {
              "Amount": 0,
              "Currency": "string",
              "Description": "string",
              "IsPaid": true,
              "IsPrimary": true,
              "SemanticsCode": "string",
              "SemanticsVendorType": "string",
              "StartDateLocal": "string",
              "Vendor": "string",
              "VendorChargeCode": "string"
            }
          ],
          "Rate": [
            {
              "Amount": 0,
              "Currency": "string",
              "Description": "string",
              "IsPaid": true,
              "IsPrimary": true,
              "NumUnits": 0,
              "PerUnit": "string",
              "SemanticsCode": "string",
              "SemanticsVendorType": "string",
              "StartDateLocal": "string",
              "Vendor": "string",
              "VendorChargeCode": "string"
            }
          ],
          "RateWithAllowance": [
            {
              "AllowanceAmount": 0,
              "AllowanceIsUnlimited": true,
              "AllowanceNumUnits": 0,
              "AllowanceUnit": "string",
              "Amount": 0,
              "Currency": "string",
              "Description": "string",
              "IsPaid": true,
              "IsPrimary": true,
              "NumUnits": 0,
              "PerUnit": "string",
              "SemanticsCode": "string",
              "SemanticsVendorType": "string",
              "StartDateLocal": "string",
              "Vendor": "string",
              "VendorChargeCode": "string"
            }
          ]
        },
        "DateCreatedUtc": "string",
        "DateModifiedUtc": "string",
        "PassengerName": "string",
        "PlatingCarrierNumericCode": "string",
        "PlatingControlNumber": "string",
        "RecordLocator": "string",
        "Taxes": [
          {
            "TaxAmount": 0,
            "TaxAuthority": "string",
            "TaxName": "string",
            "TaxRate": 0,
            "TaxType": "string"
          }
        ],
        "TotalAdjustment": 0,
        "TotalAdjustmentCurrency": "string"
      }
    ],
    "AirlineTicket": [
      {
        "AccountingLine": {
          "AirlineCode": "string",
          "AmountPaid": "string",
          "AmountPaidCurrency": "string",
          "CCNumber": "string",
          "Comment": "string",
          "Commission": "string",
          "CommissionCurrency": "string",
          "ExchangedTicketNumber": "string",
          "FOPMethod": "string",
          "Fare": "string",
          "FareCurrency": "string",
          "IssueDate": "string",
          "MCOType": "string",
          "Tax": "string",
          "TaxCurrency": "string",
          "TranControlNbr": "string",
          "TranPlatingNbr": "string"
        },
        "AddCollectAmount": 0,
        "AirlineCharges": {
          "Fixed": [
            {
              "Amount": 0,
              "Currency": "string",
              "Description": "string",
              "IsPaid": true,
              "IsPrimary": true,
              "SemanticsCode": "string",
              "SemanticsVendorType": "string",
              "StartDateLocal": "string",
              "Vendor": "string",
              "VendorChargeCode": "string"
            }
          ],
          "Percent": [
            {
              "Amount": 0,
              "Currency": "string",
              "Description": "string",
              "IsPaid": true,
              "IsPrimary": true,
              "SemanticsCode": "string",
              "SemanticsVendorType": "string",
              "StartDateLocal": "string",
              "Vendor": "string",
              "VendorChargeCode": "string"
            }
          ],
          "Rate": [
            {
              "Amount": 0,
              "Currency": "string",
              "Description": "string",
              "IsPaid": true,
              "IsPrimary": true,
              "NumUnits": 0,
              "PerUnit": "string",
              "SemanticsCode": "string",
              "SemanticsVendorType": "string",
              "StartDateLocal": "string",
              "Vendor": "string",
              "VendorChargeCode": "string"
            }
          ],
          "RateWithAllowance": [
            {
              "AllowanceAmount": 0,
              "AllowanceIsUnlimited": true,
              "AllowanceNumUnits": 0,
              "AllowanceUnit": "string",
              "Amount": 0,
              "Currency": "string",
              "Description": "string",
              "IsPaid": true,
              "IsPrimary": true,
              "NumUnits": 0,
              "PerUnit": "string",
              "SemanticsCode": "string",
              "SemanticsVendorType": "string",
              "StartDateLocal": "string",
              "Vendor": "string",
              "VendorChargeCode": "string"
            }
          ]
        },
        "AirlineTicketCoupons": [
          {
            "ClassOfService": "string",
            "CouponNumber": 0,
            "CouponStatus": "string",
            "EndCityCode": "string",
            "FlightNumber": "string",
            "NotValidAfterDate": "string",
            "NotValidBeforeDate": "string",
            "RateCode": "string",
            "StartCityCode": "string",
            "StartDateLocal": "string",
            "Status": "string",
            "TicketDesignator": "string",
            "Vendor": "string"
          }
        ],
        "AirlineTicketExchanges": [
          {
            "Amount": 0,
            "AppliedSegment1": 0,
            "AppliedSegment10": 0,
            "AppliedSegment2": 0,
            "AppliedSegment3": 0,
            "AppliedSegment4": 0,
            "AppliedSegment5": 0,
            "AppliedSegment6": 0,
            "AppliedSegment7": 0,
            "AppliedSegment8": 0,
            "AppliedSegment9": 0,
            "Currency": "string",
            "DateModifiedUtc": "string",
            "OldRecordLocator": "string",
            "PlatingCarrierNumericCode": "string",
            "PlatingControlNumber": "string"
          }
        ],
        "AirlineTicketFareBreakups": [
          {
            "BaseFare": 0,
            "ClassOfService": "string",
            "Currency": "string",
            "EndCityCode": "string",
            "IsRefundable": true,
            "StartCityCode": "string",
            "TotalFare": 0,
            "Vendor": "string"
          }
        ],
        "BaseFare": 0,
        "BaseFareCurrency": "string",
        "BaseFareNuc": 0,
        "BaseFareNucCurrency": "string",
        "ComparisonFare": 0,
        "ComparisonFareCurrency": "string",
        "DateCreatedUtc": "string",
        "DateModifiedUtc": "string",
        "Endorsements": "string",
        "InvoiceNumber": "string",
        "IssueDateTime": "string",
        "IssueDateTimeUTC": "string",
        "IssuingIataAgencyNumber": 0,
        "IssuingPseudoCity": "string",
        "LinearFareConstructor": "string",
        "MasterTicketNumber": "string",
        "NameReference": "string",
        "PassengerName": "string",
        "PlatingCarrierNumericCode": "string",
        "PlatingControlNumber": "string",
        "ProgramCarrierCode": "string",
        "ProgramMembershipNumber": "string",
        "RecordLocator": "string",
        "SabreDkNumber": "string",
        "Taxes": [
          {
            "TaxAmount": 0,
            "TaxAuthority": "string",
            "TaxName": "string",
            "TaxRate": 0,
            "TaxType": "string"
          }
        ],
        "TicketType": "string",
        "Ticketless": true,
        "TotalFare": 0,
        "TotalFareCurrency": "string",
        "TourIdentifier": "string"
      }
    ],
    "ManualAirlineTicket": [
      {
        "AirlineCharges": {
          "Fixed": [
            {
              "Amount": 0,
              "Currency": "string",
              "Description": "string",
              "IsPaid": true,
              "IsPrimary": true,
              "SemanticsCode": "string",
              "SemanticsVendorType": "string",
              "StartDateLocal": "string",
              "Vendor": "string",
              "VendorChargeCode": "string"
            }
          ],
          "Percent": [
            {
              "Amount": 0,
              "Currency": "string",
              "Description": "string",
              "IsPaid": true,
              "IsPrimary": true,
              "SemanticsCode": "string",
              "SemanticsVendorType": "string",
              "StartDateLocal": "string",
              "Vendor": "string",
              "VendorChargeCode": "string"
            }
          ],
          "Rate": [
            {
              "Amount": 0,
              "Currency": "string",
              "Description": "string",
              "IsPaid": true,
              "IsPrimary": true,
              "NumUnits": 0,
              "PerUnit": "string",
              "SemanticsCode": "string",
              "SemanticsVendorType": "string",
              "StartDateLocal": "string",
              "Vendor": "string",
              "VendorChargeCode": "string"
            }
          ],
          "RateWithAllowance": [
            {
              "AllowanceAmount": 0,
              "AllowanceIsUnlimited": true,
              "AllowanceNumUnits": 0,
              "AllowanceUnit": "string",
              "Amount": 0,
              "Currency": "string",
              "Description": "string",
              "IsPaid": true,
              "IsPrimary": true,
              "NumUnits": 0,
              "PerUnit": "string",
              "SemanticsCode": "string",
              "SemanticsVendorType": "string",
              "StartDateLocal": "string",
              "Vendor": "string",
              "VendorChargeCode": "string"
            }
          ]
        },
        "BaseFare": 0,
        "BaseFareCurrency": "string",
        "DateCreatedUtc": "string",
        "DateModifiedUtc": "string",
        "Taxes": [
          {
            "TaxAmount": 0,
            "TaxAuthority": "string",
            "TaxName": "string",
            "TaxRate": 0,
            "TaxType": "string"
          }
        ],
        "TotalFare": 0,
        "TotalFareCurrency": "string"
      }
    ]
  },
  "BookingOwner": "string",
  "BookingSource": "string",
  "Charges": {
    "Fixed": [
      {
        "Amount": 0,
        "Currency": "string",
        "Description": "string",
        "IsPaid": true,
        "IsPrimary": true,
        "SemanticsCode": "string",
        "SemanticsVendorType": "string",
        "StartDateLocal": "string",
        "Vendor": "string",
        "VendorChargeCode": "string"
      }
    ],
    "Percent": [
      {
        "Amount": 0,
        "Currency": "string",
        "Description": "string",
        "IsPaid": true,
        "IsPrimary": true,
        "SemanticsCode": "string",
        "SemanticsVendorType": "string",
        "StartDateLocal": "string",
        "Vendor": "string",
        "VendorChargeCode": "string"
      }
    ],
    "Rate": [
      {
        "Amount": 0,
        "Currency": "string",
        "Description": "string",
        "IsPaid": true,
        "IsPrimary": true,
        "NumUnits": 0,
        "PerUnit": "string",
        "SemanticsCode": "string",
        "SemanticsVendorType": "string",
        "StartDateLocal": "string",
        "Vendor": "string",
        "VendorChargeCode": "string"
      }
    ],
    "RateWithAllowance": [
      {
        "AllowanceAmount": 0,
        "AllowanceIsUnlimited": true,
        "AllowanceNumUnits": 0,
        "AllowanceUnit": "string",
        "Amount": 0,
        "Currency": "string",
        "Description": "string",
        "IsPaid": true,
        "IsPrimary": true,
        "NumUnits": 0,
        "PerUnit": "string",
        "SemanticsCode": "string",
        "SemanticsVendorType": "string",
        "StartDateLocal": "string",
        "Vendor": "string",
        "VendorChargeCode": "string"
      }
    ]
  },
  "DateBookedLocal": "string",
  "DateCreatedUtc": "string",
  "DateModifiedUtc": "string",
  "Delivery": {
    "AddressLine1": "string",
    "AddressLine2": "string",
    "City": "string",
    "Country": "string",
    "Email": "string",
    "Latitude": 0,
    "LocationAdditionalDetails": "string",
    "LocationDesc": "string",
    "LocationName": "string",
    "Longitude": 0,
    "PhoneNumber": "string",
    "ReferenceNumber": "string",
    "State": "string",
    "Type": "string",
    "Zip": "string"
  },
  "FormOfPaymentName": "string",
  "FormOfPaymentType": "string",
  "IsGhostCard": true,
  "ItinSourceName": "string",
  "LastTicketDateUtc": "string",
  "MiscChargeOrders": [
    {
      "DateCreatedUtc": "string",
      "DateModifiedUtc": "string",
      "IssueDate": "string",
      "PlatingCarrierNumericCode": "string",
      "PlatingControlNumber": "string",
      "TotalAmount": 0,
      "TotalAmountCurrency": "string"
    }
  ],
  "PassPrograms": [
    {
      "Amount": 0,
      "Name": "string",
      "Type": "string",
      "UserFirstName": "string",
      "UserLastName": "string"
    }
  ],
  "Passengers": [
    {
      "City": "string",
      "Country": "string",
      "FirstNameNumber": 0,
      "FrequentTravelerPrograms": {
        "FrequentFlyer": [
          {
            "AirlineVendor": "string",
            "Description": "string",
            "DiscountProgramExpirationDate": "string",
            "DiscountProgramType": "string",
            "FrequentFlyerNumber": "string",
            "Status": "string",
            "StatusExpirationDate": "string"
          }
        ],
        "RailProgram": [
          {
            "Description": "string",
            "DiscountProgramExpirationDate": "string",
            "DiscountProgramType": "string",
            "ProgramNumber": "string",
            "Status": "string",
            "StatusExpirationDate": "string"
          }
        ]
      },
      "LastNameNumber": 0,
      "NameFirst": "string",
      "NameLast": "string",
      "NameMiddle": "string",
      "NamePrefix": "string",
      "NameRemark": "string",
      "NameSuffix": "string",
      "NameTitle": "string",
      "PostalCode": "string",
      "State": "string",
      "StreetAddress": "string",
      "StreetAddress2": "string",
      "TextName": "string"
    }
  ],
  "PhoneNumbers": [
    {
      "Description": "string",
      "PassengerRPH": 0,
      "PhoneNumber": "string",
      "Type": "string"
    }
  ],
  "RailPayments": {
    "RailAdjustment": [
      {
        "AdjustmentDateTime": "string",
        "AdjustmentDateTimeUTC": "string",
        "AdjustmentType": "string",
        "DateCreatedUtc": "string",
        "DateModifiedUtc": "string",
        "RailCharges": {
          "Fixed": [
            {
              "Amount": 0,
              "Currency": "string",
              "Description": "string",
              "IsPaid": true,
              "IsPrimary": true,
              "SemanticsCode": "string",
              "SemanticsVendorType": "string",
              "StartDateLocal": "string",
              "Vendor": "string",
              "VendorChargeCode": "string"
            }
          ],
          "Percent": [
            {
              "Amount": 0,
              "Currency": "string",
              "Description": "string",
              "IsPaid": true,
              "IsPrimary": true,
              "SemanticsCode": "string",
              "SemanticsVendorType": "string",
              "StartDateLocal": "string",
              "Vendor": "string",
              "VendorChargeCode": "string"
            }
          ],
          "Rate": [
            {
              "Amount": 0,
              "Currency": "string",
              "Description": "string",
              "IsPaid": true,
              "IsPrimary": true,
              "NumUnits": 0,
              "PerUnit": "string",
              "SemanticsCode": "string",
              "SemanticsVendorType": "string",
              "StartDateLocal": "string",
              "Vendor": "string",
              "VendorChargeCode": "string"
            }
          ],
          "RateWithAllowance": [
            {
              "AllowanceAmount": 0,
              "AllowanceIsUnlimited": true,
              "AllowanceNumUnits": 0,
              "AllowanceUnit": "string",
              "Amount": 0,
              "Currency": "string",
              "Description": "string",
              "IsPaid": true,
              "IsPrimary": true,
              "NumUnits": 0,
              "PerUnit": "string",
              "SemanticsCode": "string",
              "SemanticsVendorType": "string",
              "StartDateLocal": "string",
              "Vendor": "string",
              "VendorChargeCode": "string"
            }
          ]
        },
        "Taxes": [
          {
            "TaxAmount": 0,
            "TaxAuthority": "string",
            "TaxName": "string",
            "TaxRate": 0,
            "TaxType": "string"
          }
        ],
        "TicketDocumentIdentifier": "string",
        "TotalAdjustment": 0,
        "TotalAdjustmentCurrency": "string"
      }
    ],
    "RailPayment": [
      {
        "BaseFare": 0,
        "BaseFareCurrency": "string",
        "DateCreatedUtc": "string",
        "DateModifiedUtc": "string",
        "IncludesVAT": true,
        "IssueByDate": "string",
        "IssueDateTime": "string",
        "IssueDateTimeUTC": "string",
        "RailCharges": {
          "Fixed": [
            {
              "Amount": 0,
              "Currency": "string",
              "Description": "string",
              "IsPaid": true,
              "IsPrimary": true,
              "SemanticsCode": "string",
              "SemanticsVendorType": "string",
              "StartDateLocal": "string",
              "Vendor": "string",
              "VendorChargeCode": "string"
            }
          ],
          "Percent": [
            {
              "Amount": 0,
              "Currency": "string",
              "Description": "string",
              "IsPaid": true,
              "IsPrimary": true,
              "SemanticsCode": "string",
              "SemanticsVendorType": "string",
              "StartDateLocal": "string",
              "Vendor": "string",
              "VendorChargeCode": "string"
            }
          ],
          "Rate": [
            {
              "Amount": 0,
              "Currency": "string",
              "Description": "string",
              "IsPaid": true,
              "IsPrimary": true,
              "NumUnits": 0,
              "PerUnit": "string",
              "SemanticsCode": "string",
              "SemanticsVendorType": "string",
              "StartDateLocal": "string",
              "Vendor": "string",
              "VendorChargeCode": "string"
            }
          ],
          "RateWithAllowance": [
            {
              "AllowanceAmount": 0,
              "AllowanceIsUnlimited": true,
              "AllowanceNumUnits": 0,
              "AllowanceUnit": "string",
              "Amount": 0,
              "Currency": "string",
              "Description": "string",
              "IsPaid": true,
              "IsPrimary": true,
              "NumUnits": 0,
              "PerUnit": "string",
              "SemanticsCode": "string",
              "SemanticsVendorType": "string",
              "StartDateLocal": "string",
              "Vendor": "string",
              "VendorChargeCode": "string"
            }
          ]
        },
        "TaxInvoice": true,
        "Taxes": [
          {
            "TaxAmount": 0,
            "TaxAuthority": "string",
            "TaxName": "string",
            "TaxRate": 0,
            "TaxType": "string"
          }
        ],
        "TicketDocumentIdentifier": "string",
        "TicketType": "string",
        "TotalFare": 0,
        "TotalFareCurrency": "string",
        "vatApplicable": true
      }
    ]
  },
  "RecordLocator": "string",
  "Remarks": {
    "TripLinkRemarks": [
      {
        "TripLinkRemark": [
          {
            "Text": "string"
          }
        ]
      }
    ]
  },
  "Segments": {
    "Air": [
      {
        "AircraftCode": "string",
        "Bags": "string",
        "Cabin": "string",
        "CancellationNumber": "string",
        "CancellationPolicy": "string",
        "CarbonEmissionLbs": 0,
        "CarbonModel": 0,
        "Charges": {
          "Fixed": [
            {
              "Amount": 0,
              "Currency": "string",
              "Description": "string",
              "IsPaid": true,
              "IsPrimary": true,
              "SemanticsCode": "string",
              "SemanticsVendorType": "string",
              "StartDateLocal": "string",
              "Vendor": "string",
              "VendorChargeCode": "string"
            }
          ],
          "Percent": [
            {
              "Amount": 0,
              "Currency": "string",
              "Description": "string",
              "IsPaid": true,
              "IsPrimary": true,
              "SemanticsCode": "string",
              "SemanticsVendorType": "string",
              "StartDateLocal": "string",
              "Vendor": "string",
              "VendorChargeCode": "string"
            }
          ],
          "Rate": [
            {
              "Amount": 0,
              "Currency": "string",
              "Description": "string",
              "IsPaid": true,
              "IsPrimary": true,
              "NumUnits": 0,
              "PerUnit": "string",
              "SemanticsCode": "string",
              "SemanticsVendorType": "string",
              "StartDateLocal": "string",
              "Vendor": "string",
              "VendorChargeCode": "string"
            }
          ],
          "RateWithAllowance": [
            {
              "AllowanceAmount": 0,
              "AllowanceIsUnlimited": true,
              "AllowanceNumUnits": 0,
              "AllowanceUnit": "string",
              "Amount": 0,
              "Currency": "string",
              "Description": "string",
              "IsPaid": true,
              "IsPrimary": true,
              "NumUnits": 0,
              "PerUnit": "string",
              "SemanticsCode": "string",
              "SemanticsVendorType": "string",
              "StartDateLocal": "string",
              "Vendor": "string",
              "VendorChargeCode": "string"
            }
          ]
        },
        "CheckedBaggage": "string",
        "ClassOfService": "string",
        "ConfirmationNumber": "string",
        "DateCancelledUtc": "string",
        "DateCreatedUtc": "string",
        "DateModifiedUtc": "string",
        "Duration": 0,
        "ETicket": "string",
        "EndCityCode": "string",
        "EndDateLocal": "string",
        "EndDateUtc": "string",
        "EndGate": "string",
        "EndTerminal": "string",
        "FlightNumber": "string",
        "FrequentTravelerId": "string",
        "IsOpenSegment": true,
        "IsPreferredVendor": 0,
        "IsUpgradeAllowed": true,
        "LegId": 0,
        "Meals": "string",
        "Miles": 0,
        "Notes": "string",
        "NumStops": 0,
        "OpenSegment": "string",
        "OperatedByFlightNumber": "string",
        "OperatedByVendor": "string",
        "OperatedByVendorName": "string",
        "Remarks": {
          "TripLinkRemarks": [
            {
              "TripLinkRemark": [
                {
                  "Text": "string"
                }
              ]
            }
          ]
        },
        "RuleViolations": [
          {
            "CompanyReasonCode": "string",
            "CompanyRuleText": "string",
            "ViolationReasonCode": 0
          }
        ],
        "Seats": [
          {
            "PassengerRph": 0,
            "SeatNumber": "string",
            "Status": "string"
          }
        ],
        "Services": "string",
        "SpecialInstructions": "string",
        "StartCityCode": "string",
        "StartDateLocal": "string",
        "StartDateUtc": "string",
        "StartGate": "string",
        "StartTerminal": "string",
        "Status": "string",
        "TimeZone": "string",
        "TimeZoneId": 0,
        "UpgradedDateTime": "string",
        "Vendor": "string",
        "VendorFlags": "string",
        "VendorName": "string"
      }
    ],
    "Car": [
      {
        "AirCondition": "string",
        "Body": "string",
        "CancellationNumber": "string",
        "Charges": {
          "Fixed": [
            {
              "Amount": 0,
              "Currency": "string",
              "Description": "string",
              "IsPaid": true,
              "IsPrimary": true,
              "SemanticsCode": "string",
              "SemanticsVendorType": "string",
              "StartDateLocal": "string",
              "Vendor": "string",
              "VendorChargeCode": "string"
            }
          ],
          "Percent": [
            {
              "Amount": 0,
              "Currency": "string",
              "Description": "string",
              "IsPaid": true,
              "IsPrimary": true,
              "SemanticsCode": "string",
              "SemanticsVendorType": "string",
              "StartDateLocal": "string",
              "Vendor": "string",
              "VendorChargeCode": "string"
            }
          ],
          "Rate": [
            {
              "Amount": 0,
              "Currency": "string",
              "Description": "string",
              "IsPaid": true,
              "IsPrimary": true,
              "NumUnits": 0,
              "PerUnit": "string",
              "SemanticsCode": "string",
              "SemanticsVendorType": "string",
              "StartDateLocal": "string",
              "Vendor": "string",
              "VendorChargeCode": "string"
            }
          ],
          "RateWithAllowance": [
            {
              "AllowanceAmount": 0,
              "AllowanceIsUnlimited": true,
              "AllowanceNumUnits": 0,
              "AllowanceUnit": "string",
              "Amount": 0,
              "Currency": "string",
              "Description": "string",
              "IsPaid": true,
              "IsPrimary": true,
              "NumUnits": 0,
              "PerUnit": "string",
              "SemanticsCode": "string",
              "SemanticsVendorType": "string",
              "StartDateLocal": "string",
              "Vendor": "string",
              "VendorChargeCode": "string"
            }
          ]
        },
        "Class": "string",
        "ConfirmationNumber": "string",
        "Currency": "string",
        "DailyRate": 0,
        "DateCancelledUtc": "string",
        "DateCreatedUtc": "string",
        "DateModifiedUtc": "string",
        "DiscountCode": "string",
        "DropoffCollectionAddress1": "string",
        "DropoffCollectionAddressType": "string",
        "DropoffCollectionCategory": "string",
        "DropoffCollectionCity": "string",
        "DropoffCollectionCityCode": "string",
        "DropoffCollectionCountry": "string",
        "DropoffCollectionLatitude": "string",
        "DropoffCollectionLongitude": "string",
        "DropoffCollectionNumber": "string",
        "DropoffCollectionPhoneNumber": "string",
        "DropoffCollectionPostalCode": "string",
        "DropoffCollectionState": "string",
        "EndAddress": "string",
        "EndAddress2": "string",
        "EndCity": "string",
        "EndCityCode": "string",
        "EndCloseTime": "string",
        "EndCountry": "string",
        "EndDateLocal": "string",
        "EndDateUtc": "string",
        "EndLatitude": 0,
        "EndLongitude": 0,
        "EndOpenTime": "string",
        "EndPhoneNumber": "string",
        "EndPostalCode": "string",
        "EndState": "string",
        "IsGhostCard": true,
        "IsPreferredVendor": 0,
        "IsUpgradeAllowed": true,
        "Notes": "string",
        "NumCars": 0,
        "NumPersons": 0,
        "PhoneNumber": "string",
        "PickupDeliveryAddress1": "string",
        "PickupDeliveryAddressType": "string",
        "PickupDeliveryCategory": "string",
        "PickupDeliveryCity": "string",
        "PickupDeliveryCityCode": "string",
        "PickupDeliveryCountry": "string",
        "PickupDeliveryLatitude": "string",
        "PickupDeliveryLongitude": "string",
        "PickupDeliveryNumber": "string",
        "PickupDeliveryPhoneNumber": "string",
        "PickupDeliveryPostalCode": "string",
        "PickupDeliveryState": "string",
        "RateCode": "string",
        "RateType": "string",
        "Remarks": {
          "TripLinkRemarks": [
            {
              "TripLinkRemark": [
                {
                  "Text": "string"
                }
              ]
            }
          ]
        },
        "SpecialEquipment": "string",
        "SpecialInstructions": "string",
        "StartAddress": "string",
        "StartAddress2": "string",
        "StartCity": "string",
        "StartCityCode": "string",
        "StartCloseTime": "string",
        "StartCountry": "string",
        "StartDateLocal": "string",
        "StartDateUtc": "string",
        "StartLatitude": 0,
        "StartLocation": "string",
        "StartLongitude": 0,
        "StartOpenTime": "string",
        "StartPostalCode": "string",
        "StartState": "string",
        "Status": "string",
        "TimeZone": "string",
        "TimeZoneId": 0,
        "TotalRate": 0,
        "Transmission": "string",
        "UpgradedDateTime": "string",
        "Vendor": "string",
        "VendorFlags": "string",
        "VendorName": "string"
      }
    ],
    "Dining": [
      {
        "CancellationNumber": "string",
        "Charges": {
          "Fixed": [
            {
              "Amount": 0,
              "Currency": "string",
              "Description": "string",
              "IsPaid": true,
              "IsPrimary": true,
              "SemanticsCode": "string",
              "SemanticsVendorType": "string",
              "StartDateLocal": "string",
              "Vendor": "string",
              "VendorChargeCode": "string"
            }
          ],
          "Percent": [
            {
              "Amount": 0,
              "Currency": "string",
              "Description": "string",
              "IsPaid": true,
              "IsPrimary": true,
              "SemanticsCode": "string",
              "SemanticsVendorType": "string",
              "StartDateLocal": "string",
              "Vendor": "string",
              "VendorChargeCode": "string"
            }
          ],
          "Rate": [
            {
              "Amount": 0,
              "Currency": "string",
              "Description": "string",
              "IsPaid": true,
              "IsPrimary": true,
              "NumUnits": 0,
              "PerUnit": "string",
              "SemanticsCode": "string",
              "SemanticsVendorType": "string",
              "StartDateLocal": "string",
              "Vendor": "string",
              "VendorChargeCode": "string"
            }
          ],
          "RateWithAllowance": [
            {
              "AllowanceAmount": 0,
              "AllowanceIsUnlimited": true,
              "AllowanceNumUnits": 0,
              "AllowanceUnit": "string",
              "Amount": 0,
              "Currency": "string",
              "Description": "string",
              "IsPaid": true,
              "IsPrimary": true,
              "NumUnits": 0,
              "PerUnit": "string",
              "SemanticsCode": "string",
              "SemanticsVendorType": "string",
              "StartDateLocal": "string",
              "Vendor": "string",
              "VendorChargeCode": "string"
            }
          ]
        },
        "ConfirmationNumber": "string",
        "DateCancelledUtc": "string",
        "DateCreatedUtc": "string",
        "DateModifiedUtc": "string",
        "EndDateLocal": "string",
        "EndDateUtc": "string",
        "FrequentTravelerId": "string",
        "IsPreferredVendor": 0,
        "IsUpgradeAllowed": true,
        "Name": "string",
        "Notes": "string",
        "NumPersons": 0,
        "PhoneNumber": "string",
        "Remarks": {
          "TripLinkRemarks": [
            {
              "TripLinkRemark": [
                {
                  "Text": "string"
                }
              ]
            }
          ]
        },
        "ReservationId": "string",
        "StartAddress": "string",
        "StartAddress2": "string",
        "StartCity": "string",
        "StartCountry": "string",
        "StartDateLocal": "string",
        "StartDateUtc": "string",
        "StartLatitude": 0,
        "StartLongitude": 0,
        "StartPostalCode": "string",
        "StartState": "string",
        "Status": "string",
        "TimeZone": "string",
        "TimeZoneId": 0,
        "UpgradedDateTime": "string",
        "Vendor": "string",
        "VendorFlags": "string",
        "VendorName": "string"
      }
    ],
    "Hotel": [
      {
        "Breakfast": true,
        "CancellationNumber": "string",
        "CancellationPolicy": "string",
        "Charges": {
          "Fixed": [
            {
              "Amount": 0,
              "Currency": "string",
              "Description": "string",
              "IsPaid": true,
              "IsPrimary": true,
              "SemanticsCode": "string",
              "SemanticsVendorType": "string",
              "StartDateLocal": "string",
              "Vendor": "string",
              "VendorChargeCode": "string"
            }
          ],
          "Percent": [
            {
              "Amount": 0,
              "Currency": "string",
              "Description": "string",
              "IsPaid": true,
              "IsPrimary": true,
              "SemanticsCode": "string",
              "SemanticsVendorType": "string",
              "StartDateLocal": "string",
              "Vendor": "string",
              "VendorChargeCode": "string"
            }
          ],
          "Rate": [
            {
              "Amount": 0,
              "Currency": "string",
              "Description": "string",
              "IsPaid": true,
              "IsPrimary": true,
              "NumUnits": 0,
              "PerUnit": "string",
              "SemanticsCode": "string",
              "SemanticsVendorType": "string",
              "StartDateLocal": "string",
              "Vendor": "string",
              "VendorChargeCode": "string"
            }
          ],
          "RateWithAllowance": [
            {
              "AllowanceAmount": 0,
              "AllowanceIsUnlimited": true,
              "AllowanceNumUnits": 0,
              "AllowanceUnit": "string",
              "Amount": 0,
              "Currency": "string",
              "Description": "string",
              "IsPaid": true,
              "IsPrimary": true,
              "NumUnits": 0,
              "PerUnit": "string",
              "SemanticsCode": "string",
              "SemanticsVendorType": "string",
              "StartDateLocal": "string",
              "Vendor": "string",
              "VendorChargeCode": "string"
            }
          ]
        },
        "CheckinTime": "string",
        "CheckoutTime": "string",
        "ConfirmationNumber": "string",
        "Currency": "string",
        "DailyRate": 0,
        "DateCancelledUtc": "string",
        "DateCreatedUtc": "string",
        "DateModifiedUtc": "string",
        "DirectBill": true,
        "DiscountCode": "string",
        "Email": "string",
        "EndDateLocal": "string",
        "EndDateUtc": "string",
        "EquipmentCode": "string",
        "FaxNumber": "string",
        "FrequentTravelerId": "string",
        "HotelPropertyId": "string",
        "IncludedCustomAmenities": "string",
        "IsGhostCard": true,
        "IsPreferredVendor": 0,
        "IsUpgradeAllowed": true,
        "ModificationCode": "string",
        "Name": "string",
        "Notes": "string",
        "NumPersons": 0,
        "NumRooms": 0,
        "Parking": true,
        "PartnerMembershipId": "string",
        "PassiveType": "string",
        "PhoneNumber": "string",
        "RateAccess": "string",
        "RateCode": "string",
        "RateType": "string",
        "Remarks": {
          "TripLinkRemarks": [
            {
              "TripLinkRemark": [
                {
                  "Text": "string"
                }
              ]
            }
          ]
        },
        "RoomDescription": "string",
        "RoomType": "string",
        "SpecialInstructions": "string",
        "StartAddress": "string",
        "StartAddress2": "string",
        "StartCity": "string",
        "StartCityCode": "string",
        "StartCountry": "string",
        "StartDateLocal": "string",
        "StartDateUtc": "string",
        "StartLatitude": 0,
        "StartLongitude": 0,
        "StartPostalCode": "string",
        "StartState": "string",
        "Status": "string",
        "TimeZone": "string",
        "TimeZoneId": 0,
        "TotalRate": 0,
        "UpgradedDateTime": "string",
        "Vendor": "string",
        "VendorFlags": "string",
        "VendorName": "string",
        "Wifi": true
      }
    ],
    "Parking": [
      {
        "CancellationNumber": "string",
        "Charges": {
          "Fixed": [
            {
              "Amount": 0,
              "Currency": "string",
              "Description": "string",
              "IsPaid": true,
              "IsPrimary": true,
              "SemanticsCode": "string",
              "SemanticsVendorType": "string",
              "StartDateLocal": "string",
              "Vendor": "string",
              "VendorChargeCode": "string"
            }
          ],
          "Percent": [
            {
              "Amount": 0,
              "Currency": "string",
              "Description": "string",
              "IsPaid": true,
              "IsPrimary": true,
              "SemanticsCode": "string",
              "SemanticsVendorType": "string",
              "StartDateLocal": "string",
              "Vendor": "string",
              "VendorChargeCode": "string"
            }
          ],
          "Rate": [
            {
              "Amount": 0,
              "Currency": "string",
              "Description": "string",
              "IsPaid": true,
              "IsPrimary": true,
              "NumUnits": 0,
              "PerUnit": "string",
              "SemanticsCode": "string",
              "SemanticsVendorType": "string",
              "StartDateLocal": "string",
              "Vendor": "string",
              "VendorChargeCode": "string"
            }
          ],
          "RateWithAllowance": [
            {
              "AllowanceAmount": 0,
              "AllowanceIsUnlimited": true,
              "AllowanceNumUnits": 0,
              "AllowanceUnit": "string",
              "Amount": 0,
              "Currency": "string",
              "Description": "string",
              "IsPaid": true,
              "IsPrimary": true,
              "NumUnits": 0,
              "PerUnit": "string",
              "SemanticsCode": "string",
              "SemanticsVendorType": "string",
              "StartDateLocal": "string",
              "Vendor": "string",
              "VendorChargeCode": "string"
            }
          ]
        },
        "ClassOfService": "string",
        "ConfirmationNumber": "string",
        "Currency": "string",
        "DateCancelledUtc": "string",
        "DateCreatedUtc": "string",
        "DateModifiedUtc": "string",
        "EndDateLocal": "string",
        "EndDateUtc": "string",
        "FrequentTravelerId": "string",
        "IsPreferredVendor": 0,
        "IsUpgradeAllowed": true,
        "Name": "string",
        "Notes": "string",
        "OperatedByVendor": "string",
        "ParkingLocationId": "string",
        "PhoneNumber": "string",
        "Pin": "string",
        "RateCode": "string",
        "Remarks": {
          "TripLinkRemarks": [
            {
              "TripLinkRemark": [
                {
                  "Text": "string"
                }
              ]
            }
          ]
        },
        "StartAddress": "string",
        "StartAddress2": "string",
        "StartCity": "string",
        "StartCityCode": "string",
        "StartCountry": "string",
        "StartDateLocal": "string",
        "StartDateUtc": "string",
        "StartLocation": "string",
        "StartPostalCode": "string",
        "StartState": "string",
        "Status": "string",
        "TimeZone": "string",
        "TimeZoneId": 0,
        "TotalRate": 0,
        "UpgradedDateTime": "string",
        "Vendor": "string",
        "VendorFlags": "string",
        "VendorName": "string"
      }
    ],
    "Rail": [
      {
        "Amenities": "string",
        "Cabin": "string",
        "CancellationNumber": "string",
        "CarbonEmissionLbs": 0,
        "CarbonModel": 0,
        "Charges": {
          "Fixed": [
            {
              "Amount": 0,
              "Currency": "string",
              "Description": "string",
              "IsPaid": true,
              "IsPrimary": true,
              "SemanticsCode": "string",
              "SemanticsVendorType": "string",
              "StartDateLocal": "string",
              "Vendor": "string",
              "VendorChargeCode": "string"
            }
          ],
          "Percent": [
            {
              "Amount": 0,
              "Currency": "string",
              "Description": "string",
              "IsPaid": true,
              "IsPrimary": true,
              "SemanticsCode": "string",
              "SemanticsVendorType": "string",
              "StartDateLocal": "string",
              "Vendor": "string",
              "VendorChargeCode": "string"
            }
          ],
          "Rate": [
            {
              "Amount": 0,
              "Currency": "string",
              "Description": "string",
              "IsPaid": true,
              "IsPrimary": true,
              "NumUnits": 0,
              "PerUnit": "string",
              "SemanticsCode": "string",
              "SemanticsVendorType": "string",
              "StartDateLocal": "string",
              "Vendor": "string",
              "VendorChargeCode": "string"
            }
          ],
          "RateWithAllowance": [
            {
              "AllowanceAmount": 0,
              "AllowanceIsUnlimited": true,
              "AllowanceNumUnits": 0,
              "AllowanceUnit": "string",
              "Amount": 0,
              "Currency": "string",
              "Description": "string",
              "IsPaid": true,
              "IsPrimary": true,
              "NumUnits": 0,
              "PerUnit": "string",
              "SemanticsCode": "string",
              "SemanticsVendorType": "string",
              "StartDateLocal": "string",
              "Vendor": "string",
              "VendorChargeCode": "string"
            }
          ]
        },
        "ClassOfService": "string",
        "ConfirmationNumber": "string",
        "Currency": "string",
        "DateCancelledUtc": "string",
        "DateCreatedUtc": "string",
        "DateModifiedUtc": "string",
        "DiscountCode": "string",
        "Duration": 0,
        "ETicket": "string",
        "EndCity": "string",
        "EndCityCode": "string",
        "EndCountry": "string",
        "EndDateLocal": "string",
        "EndDateUtc": "string",
        "EndLatitude": 0,
        "EndLongitude": 0,
        "EndPlatform": "string",
        "EndRailStation": "string",
        "EndRailStationName": "string",
        "EndState": "string",
        "FrequentTravelerId": "string",
        "IsPreferredVendor": 0,
        "IsUpgradeAllowed": true,
        "LegId": 0,
        "Meals": "string",
        "Miles": 0,
        "Notes": "string",
        "NumPersons": 0,
        "NumStops": 0,
        "OperatedByTrainNumber": "string",
        "OperatedByVendor": "string",
        "RateCode": "string",
        "Remarks": {
          "TripLinkRemarks": [
            {
              "TripLinkRemark": [
                {
                  "Text": "string"
                }
              ]
            }
          ]
        },
        "RouteRestrictCode": "string",
        "Seats": [
          {
            "Amenities": "string",
            "BerthPosition": "string",
            "Deck": "string",
            "FacingForward": "string",
            "FareSpaceComfort": "string",
            "PassengerRph": 0,
            "SeatNumber": "string",
            "SeatPosition": "string",
            "SeatType": "string",
            "SpaceType": "string",
            "Status": "string",
            "WagonNumber": "string",
            "WagonType": "string"
          }
        ],
        "SpecialInstructions": "string",
        "StartCity": "string",
        "StartCityCode": "string",
        "StartCountry": "string",
        "StartDateLocal": "string",
        "StartDateUtc": "string",
        "StartLatitude": 0,
        "StartLongitude": 0,
        "StartPlatform": "string",
        "StartRailStation": "string",
        "StartRailStationName": "string",
        "StartState": "string",
        "Status": "string",
        "TimeZone": "string",
        "TimeZoneId": 0,
        "TotalRate": 0,
        "TrainNumber": "string",
        "TrainTypeCode": "string",
        "TrainTypeName": "string",
        "TransportMode": "string",
        "UpgradedDateTime": "string",
        "Vendor": "string",
        "VendorFlags": "string",
        "VendorName": "string",
        "WagonNumber": "string"
      }
    ],
    "Ride": [
      {
        "CancellationNumber": "string",
        "CancellationPolicy": "string",
        "Charges": {
          "Fixed": [
            {
              "Amount": 0,
              "Currency": "string",
              "Description": "string",
              "IsPaid": true,
              "IsPrimary": true,
              "SemanticsCode": "string",
              "SemanticsVendorType": "string",
              "StartDateLocal": "string",
              "Vendor": "string",
              "VendorChargeCode": "string"
            }
          ],
          "Percent": [
            {
              "Amount": 0,
              "Currency": "string",
              "Description": "string",
              "IsPaid": true,
              "IsPrimary": true,
              "SemanticsCode": "string",
              "SemanticsVendorType": "string",
              "StartDateLocal": "string",
              "Vendor": "string",
              "VendorChargeCode": "string"
            }
          ],
          "Rate": [
            {
              "Amount": 0,
              "Currency": "string",
              "Description": "string",
              "IsPaid": true,
              "IsPrimary": true,
              "NumUnits": 0,
              "PerUnit": "string",
              "SemanticsCode": "string",
              "SemanticsVendorType": "string",
              "StartDateLocal": "string",
              "Vendor": "string",
              "VendorChargeCode": "string"
            }
          ],
          "RateWithAllowance": [
            {
              "AllowanceAmount": 0,
              "AllowanceIsUnlimited": true,
              "AllowanceNumUnits": 0,
              "AllowanceUnit": "string",
              "Amount": 0,
              "Currency": "string",
              "Description": "string",
              "IsPaid": true,
              "IsPrimary": true,
              "NumUnits": 0,
              "PerUnit": "string",
              "SemanticsCode": "string",
              "SemanticsVendorType": "string",
              "StartDateLocal": "string",
              "Vendor": "string",
              "VendorChargeCode": "string"
            }
          ]
        },
        "ConfirmationNumber": "string",
        "Currency": "string",
        "DateCancelledUtc": "string",
        "DateCreatedUtc": "string",
        "DateModifiedUtc": "string",
        "DropoffInstructions": "string",
        "Duration": 0,
        "EndAddress": "string",
        "EndAddress2": "string",
        "EndCity": "string",
        "EndCityCode": "string",
        "EndCountry": "string",
        "EndDateLocal": "string",
        "EndDateUtc": "string",
        "EndLatitude": 0,
        "EndLocationCode": "string",
        "EndLongitude": 0,
        "EndPostalCode": "string",
        "EndState": "string",
        "IsGhostCard": true,
        "IsPreferredVendor": 0,
        "IsUpgradeAllowed": true,
        "MeetingInstructions": "string",
        "Miles": 0,
        "Name": "string",
        "Notes": "string",
        "NumPersons": 0,
        "NumberOfHours": 0,
        "OperatedByVendorName": "string",
        "PassiveCityCode": "string",
        "PhoneNumber": "string",
        "PickupInstructions": "string",
        "ProviderFeedback": "string",
        "Rate": 0,
        "RateDescription": "string",
        "RateNotes": "string",
        "RateType": "string",
        "Remarks": {
          "TripLinkRemarks": [
            {
              "TripLinkRemark": [
                {
                  "Text": "string"
                }
              ]
            }
          ]
        },
        "ReservationId": "string",
        "SpecialInstructions": "string",
        "StartAddress": "string",
        "StartAddress2": "string",
        "StartCity": "string",
        "StartCityCode": "string",
        "StartCountry": "string",
        "StartDateLocal": "string",
        "StartDateUtc": "string",
        "StartLatitude": 0,
        "StartLocation": "string",
        "StartLocationCode": "string",
        "StartLocationName": "string",
        "StartLongitude": 0,
        "StartPostalCode": "string",
        "StartState": "string",
        "TimeZone": "string",
        "TimeZoneId": 0,
        "TotalRate": 0,
        "UpgradedDateTime": "string",
        "Vendor": "string",
        "VendorFlags": "string",
        "VendorName": "string"
      }
    ],
    "Travel": [
      {
        "CancellationNumber": "string",
        "Charges": {
          "Fixed": [
            {
              "Amount": 0,
              "Currency": "string",
              "Description": "string",
              "IsPaid": true,
              "IsPrimary": true,
              "SemanticsCode": "string",
              "SemanticsVendorType": "string",
              "StartDateLocal": "string",
              "Vendor": "string",
              "VendorChargeCode": "string"
            }
          ],
          "Percent": [
            {
              "Amount": 0,
              "Currency": "string",
              "Description": "string",
              "IsPaid": true,
              "IsPrimary": true,
              "SemanticsCode": "string",
              "SemanticsVendorType": "string",
              "StartDateLocal": "string",
              "Vendor": "string",
              "VendorChargeCode": "string"
            }
          ],
          "Rate": [
            {
              "Amount": 0,
              "Currency": "string",
              "Description": "string",
              "IsPaid": true,
              "IsPrimary": true,
              "NumUnits": 0,
              "PerUnit": "string",
              "SemanticsCode": "string",
              "SemanticsVendorType": "string",
              "StartDateLocal": "string",
              "Vendor": "string",
              "VendorChargeCode": "string"
            }
          ],
          "RateWithAllowance": [
            {
              "AllowanceAmount": 0,
              "AllowanceIsUnlimited": true,
              "AllowanceNumUnits": 0,
              "AllowanceUnit": "string",
              "Amount": 0,
              "Currency": "string",
              "Description": "string",
              "IsPaid": true,
              "IsPrimary": true,
              "NumUnits": 0,
              "PerUnit": "string",
              "SemanticsCode": "string",
              "SemanticsVendorType": "string",
              "StartDateLocal": "string",
              "Vendor": "string",
              "VendorChargeCode": "string"
            }
          ]
        },
        "ConfirmationNumber": "string",
        "Currency": "string",
        "DailyRate": 0,
        "DateCancelledUtc": "string",
        "DateCreatedUtc": "string",
        "DateModifiedUtc": "string",
        "EndAddress": "string",
        "EndAddress2": "string",
        "EndCity": "string",
        "EndCityCode": "string",
        "EndCountry": "string",
        "EndDateLocal": "string",
        "EndDateUtc": "string",
        "EndLatitude": 0,
        "EndLocation": "string",
        "EndLongitude": 0,
        "EndPostalCode": "string",
        "EndState": "string",
        "IsGhostCard": true,
        "Notes": "string",
        "NumPersons": 0,
        "PhoneNumber": "string",
        "Remarks": {
          "TripLinkRemarks": [
            {
              "TripLinkRemark": [
                {
                  "Text": "string"
                }
              ]
            }
          ]
        },
        "SpecialInstructions": "string",
        "StartAddress": "string",
        "StartAddress2": "string",
        "StartCity": "string",
        "StartCityCode": "string",
        "StartCountry": "string",
        "StartDateLocal": "string",
        "StartDateUtc": "string",
        "StartLatitude": 0,
        "StartLocation": "string",
        "StartLongitude": 0,
        "StartPostalCode": "string",
        "StartState": "string",
        "Status": "string",
        "TimeZone": "string",
        "TimeZoneId": 0,
        "TotalRate": 0,
        "TransportMode": "string",
        "Vendor": "string",
        "VendorName": "string"
      }
    ]
  },
  "TicketMailingAddress": "string",
  "TicketPickupLocation": "string",
  "TicketPickupNumber": "string",
  "WaitListSegments": {
    "SegmentOption": [
      {
        "Flight": [
          {
            "ArrAirp": "string",
            "Cabin": "string",
            "Carrier": "string",
            "DepAirp": "string",
            "FlightNum": "string"
          }
        ],
        "SegmentIndex": "string",
        "StatusCode": "string",
        "TimeStamp": "string"
      }
    ]
  },
  "Warnings": [
    {
      "Code": [
        "string"
      ],
      "Text": [
        "string"
      ],
      "Type": [
        "string"
      ]
    }
  ],
  "WebAddresses": [
    {
      "Description": "string",
      "Format": "string",
      "PassengerRPH": 0,
      "Type": "string",
      "WebAddress": "string"
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|AgencyName|string|false|none|none|
|AgencyPCC|string|false|none|none|
|AirfareQuotes|[[Quote](#schemaquote)]|false|none|none|
|AirlineTickets|[BaseAirlineTicket](#schemabaseairlineticket)|false|none|none|
|BookingOwner|string|false|none|none|
|BookingSource|string|false|none|none|
|Charges|[ChargeDetail](#schemachargedetail)|false|none|none|
|DateBookedLocal|string|false|none|none|
|DateCreatedUtc|string|false|none|none|
|DateModifiedUtc|string|false|none|none|
|Delivery|[Delivery](#schemadelivery)|false|none|none|
|FormOfPaymentName|string|false|none|none|
|FormOfPaymentType|string|false|none|none|
|IsGhostCard|boolean|false|none|none|
|ItinSourceName|string|false|none|none|
|LastTicketDateUtc|string|false|none|none|
|MiscChargeOrders|[[MiscellaneousChargeOrder](#schemamiscellaneouschargeorder)]|false|none|none|
|PassPrograms|[[PassProgram](#schemapassprogram)]|false|none|none|
|Passengers|[[Passenger](#schemapassenger)]|false|none|none|
|PhoneNumbers|[[PhoneNumberData](#schemaphonenumberdata)]|false|none|none|
|RailPayments|[BaseRailPayment](#schemabaserailpayment)|false|none|none|
|RecordLocator|string|false|none|none|
|Remarks|[Remarks](#schemaremarks)|false|none|none|
|Segments|[Segment](#schemasegment)|false|none|none|
|TicketMailingAddress|string|false|none|none|
|TicketPickupLocation|string|false|none|none|
|TicketPickupNumber|string|false|none|none|
|WaitListSegments|[WaitListSegments](#schemawaitlistsegments)|false|none|none|
|Warnings|[[Warning](#schemawarning)]|false|none|none|
|WebAddresses|[[WebAddressData](#schemawebaddressdata)]|false|none|none|

<h2 id="tocS_Car">Car</h2>
<!-- backwards compatibility -->
<a id="schemacar"></a>
<a id="schema_Car"></a>
<a id="tocScar"></a>
<a id="tocscar"></a>

```json
{
  "AirCondition": "string",
  "Body": "string",
  "CancellationNumber": "string",
  "Charges": {
    "Fixed": [
      {
        "Amount": 0,
        "Currency": "string",
        "Description": "string",
        "IsPaid": true,
        "IsPrimary": true,
        "SemanticsCode": "string",
        "SemanticsVendorType": "string",
        "StartDateLocal": "string",
        "Vendor": "string",
        "VendorChargeCode": "string"
      }
    ],
    "Percent": [
      {
        "Amount": 0,
        "Currency": "string",
        "Description": "string",
        "IsPaid": true,
        "IsPrimary": true,
        "SemanticsCode": "string",
        "SemanticsVendorType": "string",
        "StartDateLocal": "string",
        "Vendor": "string",
        "VendorChargeCode": "string"
      }
    ],
    "Rate": [
      {
        "Amount": 0,
        "Currency": "string",
        "Description": "string",
        "IsPaid": true,
        "IsPrimary": true,
        "NumUnits": 0,
        "PerUnit": "string",
        "SemanticsCode": "string",
        "SemanticsVendorType": "string",
        "StartDateLocal": "string",
        "Vendor": "string",
        "VendorChargeCode": "string"
      }
    ],
    "RateWithAllowance": [
      {
        "AllowanceAmount": 0,
        "AllowanceIsUnlimited": true,
        "AllowanceNumUnits": 0,
        "AllowanceUnit": "string",
        "Amount": 0,
        "Currency": "string",
        "Description": "string",
        "IsPaid": true,
        "IsPrimary": true,
        "NumUnits": 0,
        "PerUnit": "string",
        "SemanticsCode": "string",
        "SemanticsVendorType": "string",
        "StartDateLocal": "string",
        "Vendor": "string",
        "VendorChargeCode": "string"
      }
    ]
  },
  "Class": "string",
  "ConfirmationNumber": "string",
  "Currency": "string",
  "DailyRate": 0,
  "DateCancelledUtc": "string",
  "DateCreatedUtc": "string",
  "DateModifiedUtc": "string",
  "DiscountCode": "string",
  "DropoffCollectionAddress1": "string",
  "DropoffCollectionAddressType": "string",
  "DropoffCollectionCategory": "string",
  "DropoffCollectionCity": "string",
  "DropoffCollectionCityCode": "string",
  "DropoffCollectionCountry": "string",
  "DropoffCollectionLatitude": "string",
  "DropoffCollectionLongitude": "string",
  "DropoffCollectionNumber": "string",
  "DropoffCollectionPhoneNumber": "string",
  "DropoffCollectionPostalCode": "string",
  "DropoffCollectionState": "string",
  "EndAddress": "string",
  "EndAddress2": "string",
  "EndCity": "string",
  "EndCityCode": "string",
  "EndCloseTime": "string",
  "EndCountry": "string",
  "EndDateLocal": "string",
  "EndDateUtc": "string",
  "EndLatitude": 0,
  "EndLongitude": 0,
  "EndOpenTime": "string",
  "EndPhoneNumber": "string",
  "EndPostalCode": "string",
  "EndState": "string",
  "IsGhostCard": true,
  "IsPreferredVendor": 0,
  "IsUpgradeAllowed": true,
  "Notes": "string",
  "NumCars": 0,
  "NumPersons": 0,
  "PhoneNumber": "string",
  "PickupDeliveryAddress1": "string",
  "PickupDeliveryAddressType": "string",
  "PickupDeliveryCategory": "string",
  "PickupDeliveryCity": "string",
  "PickupDeliveryCityCode": "string",
  "PickupDeliveryCountry": "string",
  "PickupDeliveryLatitude": "string",
  "PickupDeliveryLongitude": "string",
  "PickupDeliveryNumber": "string",
  "PickupDeliveryPhoneNumber": "string",
  "PickupDeliveryPostalCode": "string",
  "PickupDeliveryState": "string",
  "RateCode": "string",
  "RateType": "string",
  "Remarks": {
    "TripLinkRemarks": [
      {
        "TripLinkRemark": [
          {
            "Text": "string"
          }
        ]
      }
    ]
  },
  "SpecialEquipment": "string",
  "SpecialInstructions": "string",
  "StartAddress": "string",
  "StartAddress2": "string",
  "StartCity": "string",
  "StartCityCode": "string",
  "StartCloseTime": "string",
  "StartCountry": "string",
  "StartDateLocal": "string",
  "StartDateUtc": "string",
  "StartLatitude": 0,
  "StartLocation": "string",
  "StartLongitude": 0,
  "StartOpenTime": "string",
  "StartPostalCode": "string",
  "StartState": "string",
  "Status": "string",
  "TimeZone": "string",
  "TimeZoneId": 0,
  "TotalRate": 0,
  "Transmission": "string",
  "UpgradedDateTime": "string",
  "Vendor": "string",
  "VendorFlags": "string",
  "VendorName": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|AirCondition|string|false|none|none|
|Body|string|false|none|none|
|CancellationNumber|string|false|none|none|
|Charges|[ChargeDetail](#schemachargedetail)|false|none|none|
|Class|string|false|none|none|
|ConfirmationNumber|string|false|none|none|
|Currency|string|false|none|none|
|DailyRate|number|false|none|none|
|DateCancelledUtc|string|false|none|none|
|DateCreatedUtc|string|false|none|none|
|DateModifiedUtc|string|false|none|none|
|DiscountCode|string|false|none|none|
|DropoffCollectionAddress1|string|false|none|none|
|DropoffCollectionAddressType|string|false|none|none|
|DropoffCollectionCategory|string|false|none|none|
|DropoffCollectionCity|string|false|none|none|
|DropoffCollectionCityCode|string|false|none|none|
|DropoffCollectionCountry|string|false|none|none|
|DropoffCollectionLatitude|string|false|none|none|
|DropoffCollectionLongitude|string|false|none|none|
|DropoffCollectionNumber|string|false|none|none|
|DropoffCollectionPhoneNumber|string|false|none|none|
|DropoffCollectionPostalCode|string|false|none|none|
|DropoffCollectionState|string|false|none|none|
|EndAddress|string|false|none|none|
|EndAddress2|string|false|none|none|
|EndCity|string|false|none|none|
|EndCityCode|string|false|none|none|
|EndCloseTime|string|false|none|none|
|EndCountry|string|false|none|none|
|EndDateLocal|string|false|none|none|
|EndDateUtc|string|false|none|none|
|EndLatitude|number|false|none|none|
|EndLongitude|number|false|none|none|
|EndOpenTime|string|false|none|none|
|EndPhoneNumber|string|false|none|none|
|EndPostalCode|string|false|none|none|
|EndState|string|false|none|none|
|IsGhostCard|boolean|false|none|none|
|IsPreferredVendor|integer|false|none|none|
|IsUpgradeAllowed|boolean|false|none|none|
|Notes|string|false|none|none|
|NumCars|integer|false|none|none|
|NumPersons|integer|false|none|none|
|PhoneNumber|string|false|none|none|
|PickupDeliveryAddress1|string|false|none|none|
|PickupDeliveryAddressType|string|false|none|none|
|PickupDeliveryCategory|string|false|none|none|
|PickupDeliveryCity|string|false|none|none|
|PickupDeliveryCityCode|string|false|none|none|
|PickupDeliveryCountry|string|false|none|none|
|PickupDeliveryLatitude|string|false|none|none|
|PickupDeliveryLongitude|string|false|none|none|
|PickupDeliveryNumber|string|false|none|none|
|PickupDeliveryPhoneNumber|string|false|none|none|
|PickupDeliveryPostalCode|string|false|none|none|
|PickupDeliveryState|string|false|none|none|
|RateCode|string|false|none|none|
|RateType|string|false|none|none|
|Remarks|[Remarks](#schemaremarks)|false|none|none|
|SpecialEquipment|string|false|none|none|
|SpecialInstructions|string|false|none|none|
|StartAddress|string|false|none|none|
|StartAddress2|string|false|none|none|
|StartCity|string|false|none|none|
|StartCityCode|string|false|none|none|
|StartCloseTime|string|false|none|none|
|StartCountry|string|false|none|none|
|StartDateLocal|string|false|none|none|
|StartDateUtc|string|false|none|none|
|StartLatitude|number|false|none|none|
|StartLocation|string|false|none|none|
|StartLongitude|number|false|none|none|
|StartOpenTime|string|false|none|none|
|StartPostalCode|string|false|none|none|
|StartState|string|false|none|none|
|Status|string|false|none|none|
|TimeZone|string|false|none|none|
|TimeZoneId|integer|false|none|none|
|TotalRate|number|false|none|none|
|Transmission|string|false|none|none|
|UpgradedDateTime|string|false|none|none|
|Vendor|string|false|none|none|
|VendorFlags|string|false|none|none|
|VendorName|string|false|none|none|

<h2 id="tocS_ChargeDetail">ChargeDetail</h2>
<!-- backwards compatibility -->
<a id="schemachargedetail"></a>
<a id="schema_ChargeDetail"></a>
<a id="tocSchargedetail"></a>
<a id="tocschargedetail"></a>

```json
{
  "Fixed": [
    {
      "Amount": 0,
      "Currency": "string",
      "Description": "string",
      "IsPaid": true,
      "IsPrimary": true,
      "SemanticsCode": "string",
      "SemanticsVendorType": "string",
      "StartDateLocal": "string",
      "Vendor": "string",
      "VendorChargeCode": "string"
    }
  ],
  "Percent": [
    {
      "Amount": 0,
      "Currency": "string",
      "Description": "string",
      "IsPaid": true,
      "IsPrimary": true,
      "SemanticsCode": "string",
      "SemanticsVendorType": "string",
      "StartDateLocal": "string",
      "Vendor": "string",
      "VendorChargeCode": "string"
    }
  ],
  "Rate": [
    {
      "Amount": 0,
      "Currency": "string",
      "Description": "string",
      "IsPaid": true,
      "IsPrimary": true,
      "NumUnits": 0,
      "PerUnit": "string",
      "SemanticsCode": "string",
      "SemanticsVendorType": "string",
      "StartDateLocal": "string",
      "Vendor": "string",
      "VendorChargeCode": "string"
    }
  ],
  "RateWithAllowance": [
    {
      "AllowanceAmount": 0,
      "AllowanceIsUnlimited": true,
      "AllowanceNumUnits": 0,
      "AllowanceUnit": "string",
      "Amount": 0,
      "Currency": "string",
      "Description": "string",
      "IsPaid": true,
      "IsPrimary": true,
      "NumUnits": 0,
      "PerUnit": "string",
      "SemanticsCode": "string",
      "SemanticsVendorType": "string",
      "StartDateLocal": "string",
      "Vendor": "string",
      "VendorChargeCode": "string"
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Fixed|[[Fixed](#schemafixed)]|false|none|none|
|Percent|[[Percent](#schemapercent)]|false|none|none|
|Rate|[[Rate](#schemarate)]|false|none|none|
|RateWithAllowance|[[RateWithAllowance](#schemaratewithallowance)]|false|none|none|

<h2 id="tocS_CustomAttribute">CustomAttribute</h2>
<!-- backwards compatibility -->
<a id="schemacustomattribute"></a>
<a id="schema_CustomAttribute"></a>
<a id="tocScustomattribute"></a>
<a id="tocscustomattribute"></a>

```json
{
  "Data": "string",
  "DataType": "string",
  "DisplayOnItinerary": true,
  "DisplayTitle": "string",
  "ExternalId": 0,
  "Name": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Data|string|false|none|none|
|DataType|string|false|none|none|
|DisplayOnItinerary|boolean|false|none|none|
|DisplayTitle|string|false|none|none|
|ExternalId|integer|false|none|none|
|Name|string|false|none|none|

<h2 id="tocS_Delivery">Delivery</h2>
<!-- backwards compatibility -->
<a id="schemadelivery"></a>
<a id="schema_Delivery"></a>
<a id="tocSdelivery"></a>
<a id="tocsdelivery"></a>

```json
{
  "AddressLine1": "string",
  "AddressLine2": "string",
  "City": "string",
  "Country": "string",
  "Email": "string",
  "Latitude": 0,
  "LocationAdditionalDetails": "string",
  "LocationDesc": "string",
  "LocationName": "string",
  "Longitude": 0,
  "PhoneNumber": "string",
  "ReferenceNumber": "string",
  "State": "string",
  "Type": "string",
  "Zip": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|AddressLine1|string|false|none|none|
|AddressLine2|string|false|none|none|
|City|string|false|none|none|
|Country|string|false|none|none|
|Email|string|false|none|none|
|Latitude|number|false|none|none|
|LocationAdditionalDetails|string|false|none|none|
|LocationDesc|string|false|none|none|
|LocationName|string|false|none|none|
|Longitude|number|false|none|none|
|PhoneNumber|string|false|none|none|
|ReferenceNumber|string|false|none|none|
|State|string|false|none|none|
|Type|string|true|none|none|
|Zip|string|false|none|none|

<h2 id="tocS_Dining">Dining</h2>
<!-- backwards compatibility -->
<a id="schemadining"></a>
<a id="schema_Dining"></a>
<a id="tocSdining"></a>
<a id="tocsdining"></a>

```json
{
  "CancellationNumber": "string",
  "Charges": {
    "Fixed": [
      {
        "Amount": 0,
        "Currency": "string",
        "Description": "string",
        "IsPaid": true,
        "IsPrimary": true,
        "SemanticsCode": "string",
        "SemanticsVendorType": "string",
        "StartDateLocal": "string",
        "Vendor": "string",
        "VendorChargeCode": "string"
      }
    ],
    "Percent": [
      {
        "Amount": 0,
        "Currency": "string",
        "Description": "string",
        "IsPaid": true,
        "IsPrimary": true,
        "SemanticsCode": "string",
        "SemanticsVendorType": "string",
        "StartDateLocal": "string",
        "Vendor": "string",
        "VendorChargeCode": "string"
      }
    ],
    "Rate": [
      {
        "Amount": 0,
        "Currency": "string",
        "Description": "string",
        "IsPaid": true,
        "IsPrimary": true,
        "NumUnits": 0,
        "PerUnit": "string",
        "SemanticsCode": "string",
        "SemanticsVendorType": "string",
        "StartDateLocal": "string",
        "Vendor": "string",
        "VendorChargeCode": "string"
      }
    ],
    "RateWithAllowance": [
      {
        "AllowanceAmount": 0,
        "AllowanceIsUnlimited": true,
        "AllowanceNumUnits": 0,
        "AllowanceUnit": "string",
        "Amount": 0,
        "Currency": "string",
        "Description": "string",
        "IsPaid": true,
        "IsPrimary": true,
        "NumUnits": 0,
        "PerUnit": "string",
        "SemanticsCode": "string",
        "SemanticsVendorType": "string",
        "StartDateLocal": "string",
        "Vendor": "string",
        "VendorChargeCode": "string"
      }
    ]
  },
  "ConfirmationNumber": "string",
  "DateCancelledUtc": "string",
  "DateCreatedUtc": "string",
  "DateModifiedUtc": "string",
  "EndDateLocal": "string",
  "EndDateUtc": "string",
  "FrequentTravelerId": "string",
  "IsPreferredVendor": 0,
  "IsUpgradeAllowed": true,
  "Name": "string",
  "Notes": "string",
  "NumPersons": 0,
  "PhoneNumber": "string",
  "Remarks": {
    "TripLinkRemarks": [
      {
        "TripLinkRemark": [
          {
            "Text": "string"
          }
        ]
      }
    ]
  },
  "ReservationId": "string",
  "StartAddress": "string",
  "StartAddress2": "string",
  "StartCity": "string",
  "StartCountry": "string",
  "StartDateLocal": "string",
  "StartDateUtc": "string",
  "StartLatitude": 0,
  "StartLongitude": 0,
  "StartPostalCode": "string",
  "StartState": "string",
  "Status": "string",
  "TimeZone": "string",
  "TimeZoneId": 0,
  "UpgradedDateTime": "string",
  "Vendor": "string",
  "VendorFlags": "string",
  "VendorName": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|CancellationNumber|string|false|none|none|
|Charges|[ChargeDetail](#schemachargedetail)|false|none|none|
|ConfirmationNumber|string|false|none|none|
|DateCancelledUtc|string|false|none|none|
|DateCreatedUtc|string|false|none|none|
|DateModifiedUtc|string|false|none|none|
|EndDateLocal|string|false|none|none|
|EndDateUtc|string|false|none|none|
|FrequentTravelerId|string|false|none|none|
|IsPreferredVendor|integer|false|none|none|
|IsUpgradeAllowed|boolean|false|none|none|
|Name|string|false|none|none|
|Notes|string|false|none|none|
|NumPersons|integer|false|none|none|
|PhoneNumber|string|false|none|none|
|Remarks|[Remarks](#schemaremarks)|false|none|none|
|ReservationId|string|false|none|none|
|StartAddress|string|false|none|none|
|StartAddress2|string|false|none|none|
|StartCity|string|false|none|none|
|StartCountry|string|false|none|none|
|StartDateLocal|string|false|none|none|
|StartDateUtc|string|false|none|none|
|StartLatitude|number|false|none|none|
|StartLongitude|number|false|none|none|
|StartPostalCode|string|false|none|none|
|StartState|string|false|none|none|
|Status|string|false|none|none|
|TimeZone|string|false|none|none|
|TimeZoneId|integer|false|none|none|
|UpgradedDateTime|string|false|none|none|
|Vendor|string|false|none|none|
|VendorFlags|string|false|none|none|
|VendorName|string|false|none|none|

<h2 id="tocS_Fixed">Fixed</h2>
<!-- backwards compatibility -->
<a id="schemafixed"></a>
<a id="schema_Fixed"></a>
<a id="tocSfixed"></a>
<a id="tocsfixed"></a>

```json
{
  "Amount": 0,
  "Currency": "string",
  "Description": "string",
  "IsPaid": true,
  "IsPrimary": true,
  "SemanticsCode": "string",
  "SemanticsVendorType": "string",
  "StartDateLocal": "string",
  "Vendor": "string",
  "VendorChargeCode": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Amount|number|false|none|none|
|Currency|string|false|none|none|
|Description|string|false|none|none|
|IsPaid|boolean|false|none|none|
|IsPrimary|boolean|false|none|none|
|SemanticsCode|string|false|none|none|
|SemanticsVendorType|string|false|none|none|
|StartDateLocal|string|false|none|none|
|Vendor|string|false|none|none|
|VendorChargeCode|string|false|none|none|

<h2 id="tocS_FrequentFlyer">FrequentFlyer</h2>
<!-- backwards compatibility -->
<a id="schemafrequentflyer"></a>
<a id="schema_FrequentFlyer"></a>
<a id="tocSfrequentflyer"></a>
<a id="tocsfrequentflyer"></a>

```json
{
  "AirlineVendor": "string",
  "Description": "string",
  "DiscountProgramExpirationDate": "string",
  "DiscountProgramType": "string",
  "FrequentFlyerNumber": "string",
  "Status": "string",
  "StatusExpirationDate": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|AirlineVendor|string|false|none|none|
|Description|string|false|none|none|
|DiscountProgramExpirationDate|string|false|none|none|
|DiscountProgramType|string|false|none|none|
|FrequentFlyerNumber|string|false|none|none|
|Status|string|false|none|none|
|StatusExpirationDate|string|false|none|none|

<h2 id="tocS_FrequentTravelerProgram">FrequentTravelerProgram</h2>
<!-- backwards compatibility -->
<a id="schemafrequenttravelerprogram"></a>
<a id="schema_FrequentTravelerProgram"></a>
<a id="tocSfrequenttravelerprogram"></a>
<a id="tocsfrequenttravelerprogram"></a>

```json
{
  "FrequentFlyer": [
    {
      "AirlineVendor": "string",
      "Description": "string",
      "DiscountProgramExpirationDate": "string",
      "DiscountProgramType": "string",
      "FrequentFlyerNumber": "string",
      "Status": "string",
      "StatusExpirationDate": "string"
    }
  ],
  "RailProgram": [
    {
      "Description": "string",
      "DiscountProgramExpirationDate": "string",
      "DiscountProgramType": "string",
      "ProgramNumber": "string",
      "Status": "string",
      "StatusExpirationDate": "string"
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|FrequentFlyer|[[FrequentFlyer](#schemafrequentflyer)]|false|none|none|
|RailProgram|[[RailProgram](#schemarailprogram)]|false|none|none|

<h2 id="tocS_Hotel">Hotel</h2>
<!-- backwards compatibility -->
<a id="schemahotel"></a>
<a id="schema_Hotel"></a>
<a id="tocShotel"></a>
<a id="tocshotel"></a>

```json
{
  "Breakfast": true,
  "CancellationNumber": "string",
  "CancellationPolicy": "string",
  "Charges": {
    "Fixed": [
      {
        "Amount": 0,
        "Currency": "string",
        "Description": "string",
        "IsPaid": true,
        "IsPrimary": true,
        "SemanticsCode": "string",
        "SemanticsVendorType": "string",
        "StartDateLocal": "string",
        "Vendor": "string",
        "VendorChargeCode": "string"
      }
    ],
    "Percent": [
      {
        "Amount": 0,
        "Currency": "string",
        "Description": "string",
        "IsPaid": true,
        "IsPrimary": true,
        "SemanticsCode": "string",
        "SemanticsVendorType": "string",
        "StartDateLocal": "string",
        "Vendor": "string",
        "VendorChargeCode": "string"
      }
    ],
    "Rate": [
      {
        "Amount": 0,
        "Currency": "string",
        "Description": "string",
        "IsPaid": true,
        "IsPrimary": true,
        "NumUnits": 0,
        "PerUnit": "string",
        "SemanticsCode": "string",
        "SemanticsVendorType": "string",
        "StartDateLocal": "string",
        "Vendor": "string",
        "VendorChargeCode": "string"
      }
    ],
    "RateWithAllowance": [
      {
        "AllowanceAmount": 0,
        "AllowanceIsUnlimited": true,
        "AllowanceNumUnits": 0,
        "AllowanceUnit": "string",
        "Amount": 0,
        "Currency": "string",
        "Description": "string",
        "IsPaid": true,
        "IsPrimary": true,
        "NumUnits": 0,
        "PerUnit": "string",
        "SemanticsCode": "string",
        "SemanticsVendorType": "string",
        "StartDateLocal": "string",
        "Vendor": "string",
        "VendorChargeCode": "string"
      }
    ]
  },
  "CheckinTime": "string",
  "CheckoutTime": "string",
  "ConfirmationNumber": "string",
  "Currency": "string",
  "DailyRate": 0,
  "DateCancelledUtc": "string",
  "DateCreatedUtc": "string",
  "DateModifiedUtc": "string",
  "DirectBill": true,
  "DiscountCode": "string",
  "Email": "string",
  "EndDateLocal": "string",
  "EndDateUtc": "string",
  "EquipmentCode": "string",
  "FaxNumber": "string",
  "FrequentTravelerId": "string",
  "HotelPropertyId": "string",
  "IncludedCustomAmenities": "string",
  "IsGhostCard": true,
  "IsPreferredVendor": 0,
  "IsUpgradeAllowed": true,
  "ModificationCode": "string",
  "Name": "string",
  "Notes": "string",
  "NumPersons": 0,
  "NumRooms": 0,
  "Parking": true,
  "PartnerMembershipId": "string",
  "PassiveType": "string",
  "PhoneNumber": "string",
  "RateAccess": "string",
  "RateCode": "string",
  "RateType": "string",
  "Remarks": {
    "TripLinkRemarks": [
      {
        "TripLinkRemark": [
          {
            "Text": "string"
          }
        ]
      }
    ]
  },
  "RoomDescription": "string",
  "RoomType": "string",
  "SpecialInstructions": "string",
  "StartAddress": "string",
  "StartAddress2": "string",
  "StartCity": "string",
  "StartCityCode": "string",
  "StartCountry": "string",
  "StartDateLocal": "string",
  "StartDateUtc": "string",
  "StartLatitude": 0,
  "StartLongitude": 0,
  "StartPostalCode": "string",
  "StartState": "string",
  "Status": "string",
  "TimeZone": "string",
  "TimeZoneId": 0,
  "TotalRate": 0,
  "UpgradedDateTime": "string",
  "Vendor": "string",
  "VendorFlags": "string",
  "VendorName": "string",
  "Wifi": true
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Breakfast|boolean|false|none|none|
|CancellationNumber|string|false|none|none|
|CancellationPolicy|string|false|none|none|
|Charges|[ChargeDetail](#schemachargedetail)|false|none|none|
|CheckinTime|string|false|none|none|
|CheckoutTime|string|false|none|none|
|ConfirmationNumber|string|false|none|none|
|Currency|string|false|none|none|
|DailyRate|number|false|none|none|
|DateCancelledUtc|string|false|none|none|
|DateCreatedUtc|string|false|none|none|
|DateModifiedUtc|string|false|none|none|
|DirectBill|boolean|false|none|none|
|DiscountCode|string|false|none|none|
|Email|string|false|none|none|
|EndDateLocal|string|false|none|none|
|EndDateUtc|string|false|none|none|
|EquipmentCode|string|false|none|none|
|FaxNumber|string|false|none|none|
|FrequentTravelerId|string|false|none|none|
|HotelPropertyId|string|false|none|none|
|IncludedCustomAmenities|string|false|none|none|
|IsGhostCard|boolean|false|none|none|
|IsPreferredVendor|integer|false|none|none|
|IsUpgradeAllowed|boolean|false|none|none|
|ModificationCode|string|false|none|none|
|Name|string|false|none|none|
|Notes|string|false|none|none|
|NumPersons|integer|false|none|none|
|NumRooms|integer|false|none|none|
|Parking|boolean|false|none|none|
|PartnerMembershipId|string|false|none|none|
|PassiveType|string|false|none|none|
|PhoneNumber|string|false|none|none|
|RateAccess|string|false|none|none|
|RateCode|string|false|none|none|
|RateType|string|false|none|none|
|Remarks|[Remarks](#schemaremarks)|false|none|none|
|RoomDescription|string|false|none|none|
|RoomType|string|false|none|none|
|SpecialInstructions|string|false|none|none|
|StartAddress|string|false|none|none|
|StartAddress2|string|false|none|none|
|StartCity|string|false|none|none|
|StartCityCode|string|false|none|none|
|StartCountry|string|false|none|none|
|StartDateLocal|string|false|none|none|
|StartDateUtc|string|false|none|none|
|StartLatitude|number|false|none|none|
|StartLongitude|number|false|none|none|
|StartPostalCode|string|false|none|none|
|StartState|string|false|none|none|
|Status|string|false|none|none|
|TimeZone|string|false|none|none|
|TimeZoneId|integer|false|none|none|
|TotalRate|number|false|none|none|
|UpgradedDateTime|string|false|none|none|
|Vendor|string|false|none|none|
|VendorFlags|string|false|none|none|
|VendorName|string|false|none|none|
|Wifi|boolean|false|none|none|

<h2 id="tocS_Itinerary">Itinerary</h2>
<!-- backwards compatibility -->
<a id="schemaitinerary"></a>
<a id="schema_Itinerary"></a>
<a id="tocSitinerary"></a>
<a id="tocsitinerary"></a>

```json
{
  "BookedByFirstName": "string",
  "BookedByLastName": "string",
  "BookedVia": "string",
  "Bookings": [
    {
      "AgencyName": "string",
      "AgencyPCC": "string",
      "AirfareQuotes": [
        {
          "AirlineCharges": {
            "Fixed": [
              {
                "Amount": 0,
                "Currency": "string",
                "Description": "string",
                "IsPaid": true,
                "IsPrimary": true,
                "SemanticsCode": "string",
                "SemanticsVendorType": "string",
                "StartDateLocal": "string",
                "Vendor": "string",
                "VendorChargeCode": "string"
              }
            ],
            "Percent": [
              {
                "Amount": 0,
                "Currency": "string",
                "Description": "string",
                "IsPaid": true,
                "IsPrimary": true,
                "SemanticsCode": "string",
                "SemanticsVendorType": "string",
                "StartDateLocal": "string",
                "Vendor": "string",
                "VendorChargeCode": "string"
              }
            ],
            "Rate": [
              {
                "Amount": 0,
                "Currency": "string",
                "Description": "string",
                "IsPaid": true,
                "IsPrimary": true,
                "NumUnits": 0,
                "PerUnit": "string",
                "SemanticsCode": "string",
                "SemanticsVendorType": "string",
                "StartDateLocal": "string",
                "Vendor": "string",
                "VendorChargeCode": "string"
              }
            ],
            "RateWithAllowance": [
              {
                "AllowanceAmount": 0,
                "AllowanceIsUnlimited": true,
                "AllowanceNumUnits": 0,
                "AllowanceUnit": "string",
                "Amount": 0,
                "Currency": "string",
                "Description": "string",
                "IsPaid": true,
                "IsPrimary": true,
                "NumUnits": 0,
                "PerUnit": "string",
                "SemanticsCode": "string",
                "SemanticsVendorType": "string",
                "StartDateLocal": "string",
                "Vendor": "string",
                "VendorChargeCode": "string"
              }
            ]
          },
          "BaseFare": 0,
          "BaseFareCurrency": "string",
          "BaseFareNuc": 0,
          "BaseFareNucCurrency": "string",
          "DateCreatedUtc": "string",
          "DateModifiedUtc": "string",
          "Endorsements": "string",
          "IssueByDate": "string",
          "TotalFare": 0,
          "TotalFareCurrency": "string"
        }
      ],
      "AirlineTickets": {
        "AirlineAdjustment": [
          {
            "AddCollectAmount": 0,
            "AdjustmentDateTime": "string",
            "AdjustmentDateTimeUTC": "string",
            "AdjustmentType": "string",
            "AirlineCharges": {
              "Fixed": [
                {
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ],
              "Percent": [
                {
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ],
              "Rate": [
                {
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "NumUnits": 0,
                  "PerUnit": "string",
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ],
              "RateWithAllowance": [
                {
                  "AllowanceAmount": 0,
                  "AllowanceIsUnlimited": true,
                  "AllowanceNumUnits": 0,
                  "AllowanceUnit": "string",
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "NumUnits": 0,
                  "PerUnit": "string",
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ]
            },
            "DateCreatedUtc": "string",
            "DateModifiedUtc": "string",
            "PassengerName": "string",
            "PlatingCarrierNumericCode": "string",
            "PlatingControlNumber": "string",
            "RecordLocator": "string",
            "Taxes": [
              {
                "TaxAmount": 0,
                "TaxAuthority": "string",
                "TaxName": "string",
                "TaxRate": 0,
                "TaxType": "string"
              }
            ],
            "TotalAdjustment": 0,
            "TotalAdjustmentCurrency": "string"
          }
        ],
        "AirlineTicket": [
          {
            "AccountingLine": {
              "AirlineCode": "string",
              "AmountPaid": "string",
              "AmountPaidCurrency": "string",
              "CCNumber": "string",
              "Comment": "string",
              "Commission": "string",
              "CommissionCurrency": "string",
              "ExchangedTicketNumber": "string",
              "FOPMethod": "string",
              "Fare": "string",
              "FareCurrency": "string",
              "IssueDate": "string",
              "MCOType": "string",
              "Tax": "string",
              "TaxCurrency": "string",
              "TranControlNbr": "string",
              "TranPlatingNbr": "string"
            },
            "AddCollectAmount": 0,
            "AirlineCharges": {
              "Fixed": [
                {
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ],
              "Percent": [
                {
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ],
              "Rate": [
                {
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "NumUnits": 0,
                  "PerUnit": "string",
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ],
              "RateWithAllowance": [
                {
                  "AllowanceAmount": 0,
                  "AllowanceIsUnlimited": true,
                  "AllowanceNumUnits": 0,
                  "AllowanceUnit": "string",
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "NumUnits": 0,
                  "PerUnit": "string",
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ]
            },
            "AirlineTicketCoupons": [
              {
                "ClassOfService": "string",
                "CouponNumber": 0,
                "CouponStatus": "string",
                "EndCityCode": "string",
                "FlightNumber": "string",
                "NotValidAfterDate": "string",
                "NotValidBeforeDate": "string",
                "RateCode": "string",
                "StartCityCode": "string",
                "StartDateLocal": "string",
                "Status": "string",
                "TicketDesignator": "string",
                "Vendor": "string"
              }
            ],
            "AirlineTicketExchanges": [
              {
                "Amount": 0,
                "AppliedSegment1": 0,
                "AppliedSegment10": 0,
                "AppliedSegment2": 0,
                "AppliedSegment3": 0,
                "AppliedSegment4": 0,
                "AppliedSegment5": 0,
                "AppliedSegment6": 0,
                "AppliedSegment7": 0,
                "AppliedSegment8": 0,
                "AppliedSegment9": 0,
                "Currency": "string",
                "DateModifiedUtc": "string",
                "OldRecordLocator": "string",
                "PlatingCarrierNumericCode": "string",
                "PlatingControlNumber": "string"
              }
            ],
            "AirlineTicketFareBreakups": [
              {
                "BaseFare": 0,
                "ClassOfService": "string",
                "Currency": "string",
                "EndCityCode": "string",
                "IsRefundable": true,
                "StartCityCode": "string",
                "TotalFare": 0,
                "Vendor": "string"
              }
            ],
            "BaseFare": 0,
            "BaseFareCurrency": "string",
            "BaseFareNuc": 0,
            "BaseFareNucCurrency": "string",
            "ComparisonFare": 0,
            "ComparisonFareCurrency": "string",
            "DateCreatedUtc": "string",
            "DateModifiedUtc": "string",
            "Endorsements": "string",
            "InvoiceNumber": "string",
            "IssueDateTime": "string",
            "IssueDateTimeUTC": "string",
            "IssuingIataAgencyNumber": 0,
            "IssuingPseudoCity": "string",
            "LinearFareConstructor": "string",
            "MasterTicketNumber": "string",
            "NameReference": "string",
            "PassengerName": "string",
            "PlatingCarrierNumericCode": "string",
            "PlatingControlNumber": "string",
            "ProgramCarrierCode": "string",
            "ProgramMembershipNumber": "string",
            "RecordLocator": "string",
            "SabreDkNumber": "string",
            "Taxes": [
              {
                "TaxAmount": 0,
                "TaxAuthority": "string",
                "TaxName": "string",
                "TaxRate": 0,
                "TaxType": "string"
              }
            ],
            "TicketType": "string",
            "Ticketless": true,
            "TotalFare": 0,
            "TotalFareCurrency": "string",
            "TourIdentifier": "string"
          }
        ],
        "ManualAirlineTicket": [
          {
            "AirlineCharges": {
              "Fixed": [
                {
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ],
              "Percent": [
                {
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ],
              "Rate": [
                {
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "NumUnits": 0,
                  "PerUnit": "string",
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ],
              "RateWithAllowance": [
                {
                  "AllowanceAmount": 0,
                  "AllowanceIsUnlimited": true,
                  "AllowanceNumUnits": 0,
                  "AllowanceUnit": "string",
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "NumUnits": 0,
                  "PerUnit": "string",
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ]
            },
            "BaseFare": 0,
            "BaseFareCurrency": "string",
            "DateCreatedUtc": "string",
            "DateModifiedUtc": "string",
            "Taxes": [
              {
                "TaxAmount": 0,
                "TaxAuthority": "string",
                "TaxName": "string",
                "TaxRate": 0,
                "TaxType": "string"
              }
            ],
            "TotalFare": 0,
            "TotalFareCurrency": "string"
          }
        ]
      },
      "BookingOwner": "string",
      "BookingSource": "string",
      "Charges": {
        "Fixed": [
          {
            "Amount": 0,
            "Currency": "string",
            "Description": "string",
            "IsPaid": true,
            "IsPrimary": true,
            "SemanticsCode": "string",
            "SemanticsVendorType": "string",
            "StartDateLocal": "string",
            "Vendor": "string",
            "VendorChargeCode": "string"
          }
        ],
        "Percent": [
          {
            "Amount": 0,
            "Currency": "string",
            "Description": "string",
            "IsPaid": true,
            "IsPrimary": true,
            "SemanticsCode": "string",
            "SemanticsVendorType": "string",
            "StartDateLocal": "string",
            "Vendor": "string",
            "VendorChargeCode": "string"
          }
        ],
        "Rate": [
          {
            "Amount": 0,
            "Currency": "string",
            "Description": "string",
            "IsPaid": true,
            "IsPrimary": true,
            "NumUnits": 0,
            "PerUnit": "string",
            "SemanticsCode": "string",
            "SemanticsVendorType": "string",
            "StartDateLocal": "string",
            "Vendor": "string",
            "VendorChargeCode": "string"
          }
        ],
        "RateWithAllowance": [
          {
            "AllowanceAmount": 0,
            "AllowanceIsUnlimited": true,
            "AllowanceNumUnits": 0,
            "AllowanceUnit": "string",
            "Amount": 0,
            "Currency": "string",
            "Description": "string",
            "IsPaid": true,
            "IsPrimary": true,
            "NumUnits": 0,
            "PerUnit": "string",
            "SemanticsCode": "string",
            "SemanticsVendorType": "string",
            "StartDateLocal": "string",
            "Vendor": "string",
            "VendorChargeCode": "string"
          }
        ]
      },
      "DateBookedLocal": "string",
      "DateCreatedUtc": "string",
      "DateModifiedUtc": "string",
      "Delivery": {
        "AddressLine1": "string",
        "AddressLine2": "string",
        "City": "string",
        "Country": "string",
        "Email": "string",
        "Latitude": 0,
        "LocationAdditionalDetails": "string",
        "LocationDesc": "string",
        "LocationName": "string",
        "Longitude": 0,
        "PhoneNumber": "string",
        "ReferenceNumber": "string",
        "State": "string",
        "Type": "string",
        "Zip": "string"
      },
      "FormOfPaymentName": "string",
      "FormOfPaymentType": "string",
      "IsGhostCard": true,
      "ItinSourceName": "string",
      "LastTicketDateUtc": "string",
      "MiscChargeOrders": [
        {
          "DateCreatedUtc": "string",
          "DateModifiedUtc": "string",
          "IssueDate": "string",
          "PlatingCarrierNumericCode": "string",
          "PlatingControlNumber": "string",
          "TotalAmount": 0,
          "TotalAmountCurrency": "string"
        }
      ],
      "PassPrograms": [
        {
          "Amount": 0,
          "Name": "string",
          "Type": "string",
          "UserFirstName": "string",
          "UserLastName": "string"
        }
      ],
      "Passengers": [
        {
          "City": "string",
          "Country": "string",
          "FirstNameNumber": 0,
          "FrequentTravelerPrograms": {
            "FrequentFlyer": [
              {
                "AirlineVendor": "string",
                "Description": "string",
                "DiscountProgramExpirationDate": "string",
                "DiscountProgramType": "string",
                "FrequentFlyerNumber": "string",
                "Status": "string",
                "StatusExpirationDate": "string"
              }
            ],
            "RailProgram": [
              {
                "Description": "string",
                "DiscountProgramExpirationDate": "string",
                "DiscountProgramType": "string",
                "ProgramNumber": "string",
                "Status": "string",
                "StatusExpirationDate": "string"
              }
            ]
          },
          "LastNameNumber": 0,
          "NameFirst": "string",
          "NameLast": "string",
          "NameMiddle": "string",
          "NamePrefix": "string",
          "NameRemark": "string",
          "NameSuffix": "string",
          "NameTitle": "string",
          "PostalCode": "string",
          "State": "string",
          "StreetAddress": "string",
          "StreetAddress2": "string",
          "TextName": "string"
        }
      ],
      "PhoneNumbers": [
        {
          "Description": "string",
          "PassengerRPH": 0,
          "PhoneNumber": "string",
          "Type": "string"
        }
      ],
      "RailPayments": {
        "RailAdjustment": [
          {
            "AdjustmentDateTime": "string",
            "AdjustmentDateTimeUTC": "string",
            "AdjustmentType": "string",
            "DateCreatedUtc": "string",
            "DateModifiedUtc": "string",
            "RailCharges": {
              "Fixed": [
                {
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ],
              "Percent": [
                {
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ],
              "Rate": [
                {
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "NumUnits": 0,
                  "PerUnit": "string",
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ],
              "RateWithAllowance": [
                {
                  "AllowanceAmount": 0,
                  "AllowanceIsUnlimited": true,
                  "AllowanceNumUnits": 0,
                  "AllowanceUnit": "string",
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "NumUnits": 0,
                  "PerUnit": "string",
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ]
            },
            "Taxes": [
              {
                "TaxAmount": 0,
                "TaxAuthority": "string",
                "TaxName": "string",
                "TaxRate": 0,
                "TaxType": "string"
              }
            ],
            "TicketDocumentIdentifier": "string",
            "TotalAdjustment": 0,
            "TotalAdjustmentCurrency": "string"
          }
        ],
        "RailPayment": [
          {
            "BaseFare": 0,
            "BaseFareCurrency": "string",
            "DateCreatedUtc": "string",
            "DateModifiedUtc": "string",
            "IncludesVAT": true,
            "IssueByDate": "string",
            "IssueDateTime": "string",
            "IssueDateTimeUTC": "string",
            "RailCharges": {
              "Fixed": [
                {
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ],
              "Percent": [
                {
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ],
              "Rate": [
                {
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "NumUnits": 0,
                  "PerUnit": "string",
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ],
              "RateWithAllowance": [
                {
                  "AllowanceAmount": 0,
                  "AllowanceIsUnlimited": true,
                  "AllowanceNumUnits": 0,
                  "AllowanceUnit": "string",
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "NumUnits": 0,
                  "PerUnit": "string",
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ]
            },
            "TaxInvoice": true,
            "Taxes": [
              {
                "TaxAmount": 0,
                "TaxAuthority": "string",
                "TaxName": "string",
                "TaxRate": 0,
                "TaxType": "string"
              }
            ],
            "TicketDocumentIdentifier": "string",
            "TicketType": "string",
            "TotalFare": 0,
            "TotalFareCurrency": "string",
            "vatApplicable": true
          }
        ]
      },
      "RecordLocator": "string",
      "Remarks": {
        "TripLinkRemarks": [
          {
            "TripLinkRemark": [
              {
                "Text": "string"
              }
            ]
          }
        ]
      },
      "Segments": {
        "Air": [
          {
            "AircraftCode": "string",
            "Bags": "string",
            "Cabin": "string",
            "CancellationNumber": "string",
            "CancellationPolicy": "string",
            "CarbonEmissionLbs": 0,
            "CarbonModel": 0,
            "Charges": {
              "Fixed": [
                {
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ],
              "Percent": [
                {
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ],
              "Rate": [
                {
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "NumUnits": 0,
                  "PerUnit": "string",
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ],
              "RateWithAllowance": [
                {
                  "AllowanceAmount": 0,
                  "AllowanceIsUnlimited": true,
                  "AllowanceNumUnits": 0,
                  "AllowanceUnit": "string",
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "NumUnits": 0,
                  "PerUnit": "string",
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ]
            },
            "CheckedBaggage": "string",
            "ClassOfService": "string",
            "ConfirmationNumber": "string",
            "DateCancelledUtc": "string",
            "DateCreatedUtc": "string",
            "DateModifiedUtc": "string",
            "Duration": 0,
            "ETicket": "string",
            "EndCityCode": "string",
            "EndDateLocal": "string",
            "EndDateUtc": "string",
            "EndGate": "string",
            "EndTerminal": "string",
            "FlightNumber": "string",
            "FrequentTravelerId": "string",
            "IsOpenSegment": true,
            "IsPreferredVendor": 0,
            "IsUpgradeAllowed": true,
            "LegId": 0,
            "Meals": "string",
            "Miles": 0,
            "Notes": "string",
            "NumStops": 0,
            "OpenSegment": "string",
            "OperatedByFlightNumber": "string",
            "OperatedByVendor": "string",
            "OperatedByVendorName": "string",
            "Remarks": {
              "TripLinkRemarks": [
                {
                  "TripLinkRemark": [
                    {}
                  ]
                }
              ]
            },
            "RuleViolations": [
              {
                "CompanyReasonCode": "string",
                "CompanyRuleText": "string",
                "ViolationReasonCode": 0
              }
            ],
            "Seats": [
              {
                "PassengerRph": 0,
                "SeatNumber": "string",
                "Status": "string"
              }
            ],
            "Services": "string",
            "SpecialInstructions": "string",
            "StartCityCode": "string",
            "StartDateLocal": "string",
            "StartDateUtc": "string",
            "StartGate": "string",
            "StartTerminal": "string",
            "Status": "string",
            "TimeZone": "string",
            "TimeZoneId": 0,
            "UpgradedDateTime": "string",
            "Vendor": "string",
            "VendorFlags": "string",
            "VendorName": "string"
          }
        ],
        "Car": [
          {
            "AirCondition": "string",
            "Body": "string",
            "CancellationNumber": "string",
            "Charges": {
              "Fixed": [
                {
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ],
              "Percent": [
                {
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ],
              "Rate": [
                {
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "NumUnits": 0,
                  "PerUnit": "string",
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ],
              "RateWithAllowance": [
                {
                  "AllowanceAmount": 0,
                  "AllowanceIsUnlimited": true,
                  "AllowanceNumUnits": 0,
                  "AllowanceUnit": "string",
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "NumUnits": 0,
                  "PerUnit": "string",
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ]
            },
            "Class": "string",
            "ConfirmationNumber": "string",
            "Currency": "string",
            "DailyRate": 0,
            "DateCancelledUtc": "string",
            "DateCreatedUtc": "string",
            "DateModifiedUtc": "string",
            "DiscountCode": "string",
            "DropoffCollectionAddress1": "string",
            "DropoffCollectionAddressType": "string",
            "DropoffCollectionCategory": "string",
            "DropoffCollectionCity": "string",
            "DropoffCollectionCityCode": "string",
            "DropoffCollectionCountry": "string",
            "DropoffCollectionLatitude": "string",
            "DropoffCollectionLongitude": "string",
            "DropoffCollectionNumber": "string",
            "DropoffCollectionPhoneNumber": "string",
            "DropoffCollectionPostalCode": "string",
            "DropoffCollectionState": "string",
            "EndAddress": "string",
            "EndAddress2": "string",
            "EndCity": "string",
            "EndCityCode": "string",
            "EndCloseTime": "string",
            "EndCountry": "string",
            "EndDateLocal": "string",
            "EndDateUtc": "string",
            "EndLatitude": 0,
            "EndLongitude": 0,
            "EndOpenTime": "string",
            "EndPhoneNumber": "string",
            "EndPostalCode": "string",
            "EndState": "string",
            "IsGhostCard": true,
            "IsPreferredVendor": 0,
            "IsUpgradeAllowed": true,
            "Notes": "string",
            "NumCars": 0,
            "NumPersons": 0,
            "PhoneNumber": "string",
            "PickupDeliveryAddress1": "string",
            "PickupDeliveryAddressType": "string",
            "PickupDeliveryCategory": "string",
            "PickupDeliveryCity": "string",
            "PickupDeliveryCityCode": "string",
            "PickupDeliveryCountry": "string",
            "PickupDeliveryLatitude": "string",
            "PickupDeliveryLongitude": "string",
            "PickupDeliveryNumber": "string",
            "PickupDeliveryPhoneNumber": "string",
            "PickupDeliveryPostalCode": "string",
            "PickupDeliveryState": "string",
            "RateCode": "string",
            "RateType": "string",
            "Remarks": {
              "TripLinkRemarks": [
                {
                  "TripLinkRemark": [
                    {}
                  ]
                }
              ]
            },
            "SpecialEquipment": "string",
            "SpecialInstructions": "string",
            "StartAddress": "string",
            "StartAddress2": "string",
            "StartCity": "string",
            "StartCityCode": "string",
            "StartCloseTime": "string",
            "StartCountry": "string",
            "StartDateLocal": "string",
            "StartDateUtc": "string",
            "StartLatitude": 0,
            "StartLocation": "string",
            "StartLongitude": 0,
            "StartOpenTime": "string",
            "StartPostalCode": "string",
            "StartState": "string",
            "Status": "string",
            "TimeZone": "string",
            "TimeZoneId": 0,
            "TotalRate": 0,
            "Transmission": "string",
            "UpgradedDateTime": "string",
            "Vendor": "string",
            "VendorFlags": "string",
            "VendorName": "string"
          }
        ],
        "Dining": [
          {
            "CancellationNumber": "string",
            "Charges": {
              "Fixed": [
                {
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ],
              "Percent": [
                {
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ],
              "Rate": [
                {
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "NumUnits": 0,
                  "PerUnit": "string",
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ],
              "RateWithAllowance": [
                {
                  "AllowanceAmount": 0,
                  "AllowanceIsUnlimited": true,
                  "AllowanceNumUnits": 0,
                  "AllowanceUnit": "string",
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "NumUnits": 0,
                  "PerUnit": "string",
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ]
            },
            "ConfirmationNumber": "string",
            "DateCancelledUtc": "string",
            "DateCreatedUtc": "string",
            "DateModifiedUtc": "string",
            "EndDateLocal": "string",
            "EndDateUtc": "string",
            "FrequentTravelerId": "string",
            "IsPreferredVendor": 0,
            "IsUpgradeAllowed": true,
            "Name": "string",
            "Notes": "string",
            "NumPersons": 0,
            "PhoneNumber": "string",
            "Remarks": {
              "TripLinkRemarks": [
                {
                  "TripLinkRemark": [
                    {}
                  ]
                }
              ]
            },
            "ReservationId": "string",
            "StartAddress": "string",
            "StartAddress2": "string",
            "StartCity": "string",
            "StartCountry": "string",
            "StartDateLocal": "string",
            "StartDateUtc": "string",
            "StartLatitude": 0,
            "StartLongitude": 0,
            "StartPostalCode": "string",
            "StartState": "string",
            "Status": "string",
            "TimeZone": "string",
            "TimeZoneId": 0,
            "UpgradedDateTime": "string",
            "Vendor": "string",
            "VendorFlags": "string",
            "VendorName": "string"
          }
        ],
        "Hotel": [
          {
            "Breakfast": true,
            "CancellationNumber": "string",
            "CancellationPolicy": "string",
            "Charges": {
              "Fixed": [
                {
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ],
              "Percent": [
                {
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ],
              "Rate": [
                {
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "NumUnits": 0,
                  "PerUnit": "string",
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ],
              "RateWithAllowance": [
                {
                  "AllowanceAmount": 0,
                  "AllowanceIsUnlimited": true,
                  "AllowanceNumUnits": 0,
                  "AllowanceUnit": "string",
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "NumUnits": 0,
                  "PerUnit": "string",
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ]
            },
            "CheckinTime": "string",
            "CheckoutTime": "string",
            "ConfirmationNumber": "string",
            "Currency": "string",
            "DailyRate": 0,
            "DateCancelledUtc": "string",
            "DateCreatedUtc": "string",
            "DateModifiedUtc": "string",
            "DirectBill": true,
            "DiscountCode": "string",
            "Email": "string",
            "EndDateLocal": "string",
            "EndDateUtc": "string",
            "EquipmentCode": "string",
            "FaxNumber": "string",
            "FrequentTravelerId": "string",
            "HotelPropertyId": "string",
            "IncludedCustomAmenities": "string",
            "IsGhostCard": true,
            "IsPreferredVendor": 0,
            "IsUpgradeAllowed": true,
            "ModificationCode": "string",
            "Name": "string",
            "Notes": "string",
            "NumPersons": 0,
            "NumRooms": 0,
            "Parking": true,
            "PartnerMembershipId": "string",
            "PassiveType": "string",
            "PhoneNumber": "string",
            "RateAccess": "string",
            "RateCode": "string",
            "RateType": "string",
            "Remarks": {
              "TripLinkRemarks": [
                {
                  "TripLinkRemark": [
                    {}
                  ]
                }
              ]
            },
            "RoomDescription": "string",
            "RoomType": "string",
            "SpecialInstructions": "string",
            "StartAddress": "string",
            "StartAddress2": "string",
            "StartCity": "string",
            "StartCityCode": "string",
            "StartCountry": "string",
            "StartDateLocal": "string",
            "StartDateUtc": "string",
            "StartLatitude": 0,
            "StartLongitude": 0,
            "StartPostalCode": "string",
            "StartState": "string",
            "Status": "string",
            "TimeZone": "string",
            "TimeZoneId": 0,
            "TotalRate": 0,
            "UpgradedDateTime": "string",
            "Vendor": "string",
            "VendorFlags": "string",
            "VendorName": "string",
            "Wifi": true
          }
        ],
        "Parking": [
          {
            "CancellationNumber": "string",
            "Charges": {
              "Fixed": [
                {
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ],
              "Percent": [
                {
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ],
              "Rate": [
                {
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "NumUnits": 0,
                  "PerUnit": "string",
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ],
              "RateWithAllowance": [
                {
                  "AllowanceAmount": 0,
                  "AllowanceIsUnlimited": true,
                  "AllowanceNumUnits": 0,
                  "AllowanceUnit": "string",
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "NumUnits": 0,
                  "PerUnit": "string",
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ]
            },
            "ClassOfService": "string",
            "ConfirmationNumber": "string",
            "Currency": "string",
            "DateCancelledUtc": "string",
            "DateCreatedUtc": "string",
            "DateModifiedUtc": "string",
            "EndDateLocal": "string",
            "EndDateUtc": "string",
            "FrequentTravelerId": "string",
            "IsPreferredVendor": 0,
            "IsUpgradeAllowed": true,
            "Name": "string",
            "Notes": "string",
            "OperatedByVendor": "string",
            "ParkingLocationId": "string",
            "PhoneNumber": "string",
            "Pin": "string",
            "RateCode": "string",
            "Remarks": {
              "TripLinkRemarks": [
                {
                  "TripLinkRemark": [
                    {}
                  ]
                }
              ]
            },
            "StartAddress": "string",
            "StartAddress2": "string",
            "StartCity": "string",
            "StartCityCode": "string",
            "StartCountry": "string",
            "StartDateLocal": "string",
            "StartDateUtc": "string",
            "StartLocation": "string",
            "StartPostalCode": "string",
            "StartState": "string",
            "Status": "string",
            "TimeZone": "string",
            "TimeZoneId": 0,
            "TotalRate": 0,
            "UpgradedDateTime": "string",
            "Vendor": "string",
            "VendorFlags": "string",
            "VendorName": "string"
          }
        ],
        "Rail": [
          {
            "Amenities": "string",
            "Cabin": "string",
            "CancellationNumber": "string",
            "CarbonEmissionLbs": 0,
            "CarbonModel": 0,
            "Charges": {
              "Fixed": [
                {
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ],
              "Percent": [
                {
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ],
              "Rate": [
                {
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "NumUnits": 0,
                  "PerUnit": "string",
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ],
              "RateWithAllowance": [
                {
                  "AllowanceAmount": 0,
                  "AllowanceIsUnlimited": true,
                  "AllowanceNumUnits": 0,
                  "AllowanceUnit": "string",
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "NumUnits": 0,
                  "PerUnit": "string",
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ]
            },
            "ClassOfService": "string",
            "ConfirmationNumber": "string",
            "Currency": "string",
            "DateCancelledUtc": "string",
            "DateCreatedUtc": "string",
            "DateModifiedUtc": "string",
            "DiscountCode": "string",
            "Duration": 0,
            "ETicket": "string",
            "EndCity": "string",
            "EndCityCode": "string",
            "EndCountry": "string",
            "EndDateLocal": "string",
            "EndDateUtc": "string",
            "EndLatitude": 0,
            "EndLongitude": 0,
            "EndPlatform": "string",
            "EndRailStation": "string",
            "EndRailStationName": "string",
            "EndState": "string",
            "FrequentTravelerId": "string",
            "IsPreferredVendor": 0,
            "IsUpgradeAllowed": true,
            "LegId": 0,
            "Meals": "string",
            "Miles": 0,
            "Notes": "string",
            "NumPersons": 0,
            "NumStops": 0,
            "OperatedByTrainNumber": "string",
            "OperatedByVendor": "string",
            "RateCode": "string",
            "Remarks": {
              "TripLinkRemarks": [
                {
                  "TripLinkRemark": [
                    {}
                  ]
                }
              ]
            },
            "RouteRestrictCode": "string",
            "Seats": [
              {
                "Amenities": "string",
                "BerthPosition": "string",
                "Deck": "string",
                "FacingForward": "string",
                "FareSpaceComfort": "string",
                "PassengerRph": 0,
                "SeatNumber": "string",
                "SeatPosition": "string",
                "SeatType": "string",
                "SpaceType": "string",
                "Status": "string",
                "WagonNumber": "string",
                "WagonType": "string"
              }
            ],
            "SpecialInstructions": "string",
            "StartCity": "string",
            "StartCityCode": "string",
            "StartCountry": "string",
            "StartDateLocal": "string",
            "StartDateUtc": "string",
            "StartLatitude": 0,
            "StartLongitude": 0,
            "StartPlatform": "string",
            "StartRailStation": "string",
            "StartRailStationName": "string",
            "StartState": "string",
            "Status": "string",
            "TimeZone": "string",
            "TimeZoneId": 0,
            "TotalRate": 0,
            "TrainNumber": "string",
            "TrainTypeCode": "string",
            "TrainTypeName": "string",
            "TransportMode": "string",
            "UpgradedDateTime": "string",
            "Vendor": "string",
            "VendorFlags": "string",
            "VendorName": "string",
            "WagonNumber": "string"
          }
        ],
        "Ride": [
          {
            "CancellationNumber": "string",
            "CancellationPolicy": "string",
            "Charges": {
              "Fixed": [
                {
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ],
              "Percent": [
                {
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ],
              "Rate": [
                {
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "NumUnits": 0,
                  "PerUnit": "string",
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ],
              "RateWithAllowance": [
                {
                  "AllowanceAmount": 0,
                  "AllowanceIsUnlimited": true,
                  "AllowanceNumUnits": 0,
                  "AllowanceUnit": "string",
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "NumUnits": 0,
                  "PerUnit": "string",
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ]
            },
            "ConfirmationNumber": "string",
            "Currency": "string",
            "DateCancelledUtc": "string",
            "DateCreatedUtc": "string",
            "DateModifiedUtc": "string",
            "DropoffInstructions": "string",
            "Duration": 0,
            "EndAddress": "string",
            "EndAddress2": "string",
            "EndCity": "string",
            "EndCityCode": "string",
            "EndCountry": "string",
            "EndDateLocal": "string",
            "EndDateUtc": "string",
            "EndLatitude": 0,
            "EndLocationCode": "string",
            "EndLongitude": 0,
            "EndPostalCode": "string",
            "EndState": "string",
            "IsGhostCard": true,
            "IsPreferredVendor": 0,
            "IsUpgradeAllowed": true,
            "MeetingInstructions": "string",
            "Miles": 0,
            "Name": "string",
            "Notes": "string",
            "NumPersons": 0,
            "NumberOfHours": 0,
            "OperatedByVendorName": "string",
            "PassiveCityCode": "string",
            "PhoneNumber": "string",
            "PickupInstructions": "string",
            "ProviderFeedback": "string",
            "Rate": 0,
            "RateDescription": "string",
            "RateNotes": "string",
            "RateType": "string",
            "Remarks": {
              "TripLinkRemarks": [
                {
                  "TripLinkRemark": [
                    {}
                  ]
                }
              ]
            },
            "ReservationId": "string",
            "SpecialInstructions": "string",
            "StartAddress": "string",
            "StartAddress2": "string",
            "StartCity": "string",
            "StartCityCode": "string",
            "StartCountry": "string",
            "StartDateLocal": "string",
            "StartDateUtc": "string",
            "StartLatitude": 0,
            "StartLocation": "string",
            "StartLocationCode": "string",
            "StartLocationName": "string",
            "StartLongitude": 0,
            "StartPostalCode": "string",
            "StartState": "string",
            "TimeZone": "string",
            "TimeZoneId": 0,
            "TotalRate": 0,
            "UpgradedDateTime": "string",
            "Vendor": "string",
            "VendorFlags": "string",
            "VendorName": "string"
          }
        ],
        "Travel": [
          {
            "CancellationNumber": "string",
            "Charges": {
              "Fixed": [
                {
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ],
              "Percent": [
                {
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ],
              "Rate": [
                {
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "NumUnits": 0,
                  "PerUnit": "string",
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ],
              "RateWithAllowance": [
                {
                  "AllowanceAmount": 0,
                  "AllowanceIsUnlimited": true,
                  "AllowanceNumUnits": 0,
                  "AllowanceUnit": "string",
                  "Amount": 0,
                  "Currency": "string",
                  "Description": "string",
                  "IsPaid": true,
                  "IsPrimary": true,
                  "NumUnits": 0,
                  "PerUnit": "string",
                  "SemanticsCode": "string",
                  "SemanticsVendorType": "string",
                  "StartDateLocal": "string",
                  "Vendor": "string",
                  "VendorChargeCode": "string"
                }
              ]
            },
            "ConfirmationNumber": "string",
            "Currency": "string",
            "DailyRate": 0,
            "DateCancelledUtc": "string",
            "DateCreatedUtc": "string",
            "DateModifiedUtc": "string",
            "EndAddress": "string",
            "EndAddress2": "string",
            "EndCity": "string",
            "EndCityCode": "string",
            "EndCountry": "string",
            "EndDateLocal": "string",
            "EndDateUtc": "string",
            "EndLatitude": 0,
            "EndLocation": "string",
            "EndLongitude": 0,
            "EndPostalCode": "string",
            "EndState": "string",
            "IsGhostCard": true,
            "Notes": "string",
            "NumPersons": 0,
            "PhoneNumber": "string",
            "Remarks": {
              "TripLinkRemarks": [
                {
                  "TripLinkRemark": [
                    {}
                  ]
                }
              ]
            },
            "SpecialInstructions": "string",
            "StartAddress": "string",
            "StartAddress2": "string",
            "StartCity": "string",
            "StartCityCode": "string",
            "StartCountry": "string",
            "StartDateLocal": "string",
            "StartDateUtc": "string",
            "StartLatitude": 0,
            "StartLocation": "string",
            "StartLongitude": 0,
            "StartPostalCode": "string",
            "StartState": "string",
            "Status": "string",
            "TimeZone": "string",
            "TimeZoneId": 0,
            "TotalRate": 0,
            "TransportMode": "string",
            "Vendor": "string",
            "VendorName": "string"
          }
        ]
      },
      "TicketMailingAddress": "string",
      "TicketPickupLocation": "string",
      "TicketPickupNumber": "string",
      "WaitListSegments": {
        "SegmentOption": [
          {
            "Flight": [
              {
                "ArrAirp": "string",
                "Cabin": "string",
                "Carrier": "string",
                "DepAirp": "string",
                "FlightNum": "string"
              }
            ],
            "SegmentIndex": "string",
            "StatusCode": "string",
            "TimeStamp": "string"
          }
        ]
      },
      "Warnings": [
        {
          "Code": [
            "string"
          ],
          "Text": [
            "string"
          ],
          "Type": [
            "string"
          ]
        }
      ],
      "WebAddresses": [
        {
          "Description": "string",
          "Format": "string",
          "PassengerRPH": 0,
          "Type": "string",
          "WebAddress": "string"
        }
      ]
    }
  ],
  "CancelComments": "string",
  "ClientLocator": "string",
  "Comments": "string",
  "CustomAttributes": [
    {
      "Data": "string",
      "DataType": "string",
      "DisplayOnItinerary": true,
      "DisplayTitle": "string",
      "ExternalId": 0,
      "Name": "string"
    }
  ],
  "DateBookedLocal": "string",
  "DateCreatedUtc": "string",
  "DateModifiedUtc": "string",
  "Description": "string",
  "EndDateLocal": "string",
  "EndDateUtc": "string",
  "HasOpenBookingPassive": true,
  "IsPersonal": true,
  "ItinLocator": "string",
  "ProjectName": "string",
  "StartDateLocal": "string",
  "StartDateUtc": "string",
  "TravelRequestId": "string",
  "TripLinkLocator": "string",
  "TripName": "string",
  "TripStatus": 0,
  "UserLoginId": "string",
  "id": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|BookedByFirstName|string|false|none|none|
|BookedByLastName|string|false|none|none|
|BookedVia|string|false|none|none|
|Bookings|[[Booking](#schemabooking)]|false|none|none|
|CancelComments|string|false|none|none|
|ClientLocator|string|false|none|none|
|Comments|string|false|none|none|
|CustomAttributes|[[CustomAttribute](#schemacustomattribute)]|false|none|none|
|DateBookedLocal|string|false|none|none|
|DateCreatedUtc|string|false|none|none|
|DateModifiedUtc|string|false|none|none|
|Description|string|false|none|none|
|EndDateLocal|string|false|none|none|
|EndDateUtc|string|false|none|none|
|HasOpenBookingPassive|boolean|false|none|none|
|IsPersonal|boolean|false|none|none|
|ItinLocator|string|false|none|none|
|ProjectName|string|false|none|none|
|StartDateLocal|string|false|none|none|
|StartDateUtc|string|false|none|none|
|TravelRequestId|string|false|none|none|
|TripLinkLocator|string|false|none|none|
|TripName|string|false|none|none|
|TripStatus|integer|false|none|none|
|UserLoginId|string|false|none|none|
|id|string|false|none|none|

<h2 id="tocS_ManualAirlineTicket">ManualAirlineTicket</h2>
<!-- backwards compatibility -->
<a id="schemamanualairlineticket"></a>
<a id="schema_ManualAirlineTicket"></a>
<a id="tocSmanualairlineticket"></a>
<a id="tocsmanualairlineticket"></a>

```json
{
  "AirlineCharges": {
    "Fixed": [
      {
        "Amount": 0,
        "Currency": "string",
        "Description": "string",
        "IsPaid": true,
        "IsPrimary": true,
        "SemanticsCode": "string",
        "SemanticsVendorType": "string",
        "StartDateLocal": "string",
        "Vendor": "string",
        "VendorChargeCode": "string"
      }
    ],
    "Percent": [
      {
        "Amount": 0,
        "Currency": "string",
        "Description": "string",
        "IsPaid": true,
        "IsPrimary": true,
        "SemanticsCode": "string",
        "SemanticsVendorType": "string",
        "StartDateLocal": "string",
        "Vendor": "string",
        "VendorChargeCode": "string"
      }
    ],
    "Rate": [
      {
        "Amount": 0,
        "Currency": "string",
        "Description": "string",
        "IsPaid": true,
        "IsPrimary": true,
        "NumUnits": 0,
        "PerUnit": "string",
        "SemanticsCode": "string",
        "SemanticsVendorType": "string",
        "StartDateLocal": "string",
        "Vendor": "string",
        "VendorChargeCode": "string"
      }
    ],
    "RateWithAllowance": [
      {
        "AllowanceAmount": 0,
        "AllowanceIsUnlimited": true,
        "AllowanceNumUnits": 0,
        "AllowanceUnit": "string",
        "Amount": 0,
        "Currency": "string",
        "Description": "string",
        "IsPaid": true,
        "IsPrimary": true,
        "NumUnits": 0,
        "PerUnit": "string",
        "SemanticsCode": "string",
        "SemanticsVendorType": "string",
        "StartDateLocal": "string",
        "Vendor": "string",
        "VendorChargeCode": "string"
      }
    ]
  },
  "BaseFare": 0,
  "BaseFareCurrency": "string",
  "DateCreatedUtc": "string",
  "DateModifiedUtc": "string",
  "Taxes": [
    {
      "TaxAmount": 0,
      "TaxAuthority": "string",
      "TaxName": "string",
      "TaxRate": 0,
      "TaxType": "string"
    }
  ],
  "TotalFare": 0,
  "TotalFareCurrency": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|AirlineCharges|[ChargeDetail](#schemachargedetail)|false|none|none|
|BaseFare|number|false|none|none|
|BaseFareCurrency|string|false|none|none|
|DateCreatedUtc|string|false|none|none|
|DateModifiedUtc|string|false|none|none|
|Taxes|[[Tax](#schematax)]|false|none|none|
|TotalFare|number|false|none|none|
|TotalFareCurrency|string|false|none|none|

<h2 id="tocS_MiscellaneousChargeOrder">MiscellaneousChargeOrder</h2>
<!-- backwards compatibility -->
<a id="schemamiscellaneouschargeorder"></a>
<a id="schema_MiscellaneousChargeOrder"></a>
<a id="tocSmiscellaneouschargeorder"></a>
<a id="tocsmiscellaneouschargeorder"></a>

```json
{
  "DateCreatedUtc": "string",
  "DateModifiedUtc": "string",
  "IssueDate": "string",
  "PlatingCarrierNumericCode": "string",
  "PlatingControlNumber": "string",
  "TotalAmount": 0,
  "TotalAmountCurrency": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|DateCreatedUtc|string|false|none|none|
|DateModifiedUtc|string|false|none|none|
|IssueDate|string|false|none|none|
|PlatingCarrierNumericCode|string|true|none|none|
|PlatingControlNumber|string|true|none|none|
|TotalAmount|number|true|none|none|
|TotalAmountCurrency|string|true|none|none|

<h2 id="tocS_Parking">Parking</h2>
<!-- backwards compatibility -->
<a id="schemaparking"></a>
<a id="schema_Parking"></a>
<a id="tocSparking"></a>
<a id="tocsparking"></a>

```json
{
  "CancellationNumber": "string",
  "Charges": {
    "Fixed": [
      {
        "Amount": 0,
        "Currency": "string",
        "Description": "string",
        "IsPaid": true,
        "IsPrimary": true,
        "SemanticsCode": "string",
        "SemanticsVendorType": "string",
        "StartDateLocal": "string",
        "Vendor": "string",
        "VendorChargeCode": "string"
      }
    ],
    "Percent": [
      {
        "Amount": 0,
        "Currency": "string",
        "Description": "string",
        "IsPaid": true,
        "IsPrimary": true,
        "SemanticsCode": "string",
        "SemanticsVendorType": "string",
        "StartDateLocal": "string",
        "Vendor": "string",
        "VendorChargeCode": "string"
      }
    ],
    "Rate": [
      {
        "Amount": 0,
        "Currency": "string",
        "Description": "string",
        "IsPaid": true,
        "IsPrimary": true,
        "NumUnits": 0,
        "PerUnit": "string",
        "SemanticsCode": "string",
        "SemanticsVendorType": "string",
        "StartDateLocal": "string",
        "Vendor": "string",
        "VendorChargeCode": "string"
      }
    ],
    "RateWithAllowance": [
      {
        "AllowanceAmount": 0,
        "AllowanceIsUnlimited": true,
        "AllowanceNumUnits": 0,
        "AllowanceUnit": "string",
        "Amount": 0,
        "Currency": "string",
        "Description": "string",
        "IsPaid": true,
        "IsPrimary": true,
        "NumUnits": 0,
        "PerUnit": "string",
        "SemanticsCode": "string",
        "SemanticsVendorType": "string",
        "StartDateLocal": "string",
        "Vendor": "string",
        "VendorChargeCode": "string"
      }
    ]
  },
  "ClassOfService": "string",
  "ConfirmationNumber": "string",
  "Currency": "string",
  "DateCancelledUtc": "string",
  "DateCreatedUtc": "string",
  "DateModifiedUtc": "string",
  "EndDateLocal": "string",
  "EndDateUtc": "string",
  "FrequentTravelerId": "string",
  "IsPreferredVendor": 0,
  "IsUpgradeAllowed": true,
  "Name": "string",
  "Notes": "string",
  "OperatedByVendor": "string",
  "ParkingLocationId": "string",
  "PhoneNumber": "string",
  "Pin": "string",
  "RateCode": "string",
  "Remarks": {
    "TripLinkRemarks": [
      {
        "TripLinkRemark": [
          {
            "Text": "string"
          }
        ]
      }
    ]
  },
  "StartAddress": "string",
  "StartAddress2": "string",
  "StartCity": "string",
  "StartCityCode": "string",
  "StartCountry": "string",
  "StartDateLocal": "string",
  "StartDateUtc": "string",
  "StartLocation": "string",
  "StartPostalCode": "string",
  "StartState": "string",
  "Status": "string",
  "TimeZone": "string",
  "TimeZoneId": 0,
  "TotalRate": 0,
  "UpgradedDateTime": "string",
  "Vendor": "string",
  "VendorFlags": "string",
  "VendorName": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|CancellationNumber|string|false|none|none|
|Charges|[ChargeDetail](#schemachargedetail)|false|none|none|
|ClassOfService|string|false|none|none|
|ConfirmationNumber|string|false|none|none|
|Currency|string|false|none|none|
|DateCancelledUtc|string|false|none|none|
|DateCreatedUtc|string|false|none|none|
|DateModifiedUtc|string|false|none|none|
|EndDateLocal|string|false|none|none|
|EndDateUtc|string|false|none|none|
|FrequentTravelerId|string|false|none|none|
|IsPreferredVendor|integer|false|none|none|
|IsUpgradeAllowed|boolean|false|none|none|
|Name|string|false|none|none|
|Notes|string|false|none|none|
|OperatedByVendor|string|false|none|none|
|ParkingLocationId|string|false|none|none|
|PhoneNumber|string|false|none|none|
|Pin|string|false|none|none|
|RateCode|string|false|none|none|
|Remarks|[Remarks](#schemaremarks)|false|none|none|
|StartAddress|string|false|none|none|
|StartAddress2|string|false|none|none|
|StartCity|string|false|none|none|
|StartCityCode|string|false|none|none|
|StartCountry|string|false|none|none|
|StartDateLocal|string|true|none|none|
|StartDateUtc|string|false|none|none|
|StartLocation|string|false|none|none|
|StartPostalCode|string|false|none|none|
|StartState|string|false|none|none|
|Status|string|false|none|none|
|TimeZone|string|false|none|none|
|TimeZoneId|integer|false|none|none|
|TotalRate|number|false|none|none|
|UpgradedDateTime|string|false|none|none|
|Vendor|string|false|none|none|
|VendorFlags|string|false|none|none|
|VendorName|string|false|none|none|

<h2 id="tocS_PassProgram">PassProgram</h2>
<!-- backwards compatibility -->
<a id="schemapassprogram"></a>
<a id="schema_PassProgram"></a>
<a id="tocSpassprogram"></a>
<a id="tocspassprogram"></a>

```json
{
  "Amount": 0,
  "Name": "string",
  "Type": "string",
  "UserFirstName": "string",
  "UserLastName": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Amount|number|false|none|none|
|Name|string|false|none|none|
|Type|string|false|none|none|
|UserFirstName|string|false|none|none|
|UserLastName|string|false|none|none|

<h2 id="tocS_Passenger">Passenger</h2>
<!-- backwards compatibility -->
<a id="schemapassenger"></a>
<a id="schema_Passenger"></a>
<a id="tocSpassenger"></a>
<a id="tocspassenger"></a>

```json
{
  "City": "string",
  "Country": "string",
  "FirstNameNumber": 0,
  "FrequentTravelerPrograms": {
    "FrequentFlyer": [
      {
        "AirlineVendor": "string",
        "Description": "string",
        "DiscountProgramExpirationDate": "string",
        "DiscountProgramType": "string",
        "FrequentFlyerNumber": "string",
        "Status": "string",
        "StatusExpirationDate": "string"
      }
    ],
    "RailProgram": [
      {
        "Description": "string",
        "DiscountProgramExpirationDate": "string",
        "DiscountProgramType": "string",
        "ProgramNumber": "string",
        "Status": "string",
        "StatusExpirationDate": "string"
      }
    ]
  },
  "LastNameNumber": 0,
  "NameFirst": "string",
  "NameLast": "string",
  "NameMiddle": "string",
  "NamePrefix": "string",
  "NameRemark": "string",
  "NameSuffix": "string",
  "NameTitle": "string",
  "PostalCode": "string",
  "State": "string",
  "StreetAddress": "string",
  "StreetAddress2": "string",
  "TextName": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|City|string|false|none|none|
|Country|string|false|none|none|
|FirstNameNumber|integer|false|none|none|
|FrequentTravelerPrograms|[FrequentTravelerProgram](#schemafrequenttravelerprogram)|false|none|none|
|LastNameNumber|integer|false|none|none|
|NameFirst|string|false|none|none|
|NameLast|string|false|none|none|
|NameMiddle|string|false|none|none|
|NamePrefix|string|false|none|none|
|NameRemark|string|false|none|none|
|NameSuffix|string|false|none|none|
|NameTitle|string|false|none|none|
|PostalCode|string|false|none|none|
|State|string|false|none|none|
|StreetAddress|string|false|none|none|
|StreetAddress2|string|false|none|none|
|TextName|string|false|none|none|

<h2 id="tocS_Percent">Percent</h2>
<!-- backwards compatibility -->
<a id="schemapercent"></a>
<a id="schema_Percent"></a>
<a id="tocSpercent"></a>
<a id="tocspercent"></a>

```json
{
  "Amount": 0,
  "Currency": "string",
  "Description": "string",
  "IsPaid": true,
  "IsPrimary": true,
  "SemanticsCode": "string",
  "SemanticsVendorType": "string",
  "StartDateLocal": "string",
  "Vendor": "string",
  "VendorChargeCode": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Amount|number|false|none|none|
|Currency|string|false|none|none|
|Description|string|false|none|none|
|IsPaid|boolean|false|none|none|
|IsPrimary|boolean|false|none|none|
|SemanticsCode|string|false|none|none|
|SemanticsVendorType|string|false|none|none|
|StartDateLocal|string|false|none|none|
|Vendor|string|false|none|none|
|VendorChargeCode|string|false|none|none|

<h2 id="tocS_PhoneNumberData">PhoneNumberData</h2>
<!-- backwards compatibility -->
<a id="schemaphonenumberdata"></a>
<a id="schema_PhoneNumberData"></a>
<a id="tocSphonenumberdata"></a>
<a id="tocsphonenumberdata"></a>

```json
{
  "Description": "string",
  "PassengerRPH": 0,
  "PhoneNumber": "string",
  "Type": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Description|string|false|none|none|
|PassengerRPH|integer|false|none|none|
|PhoneNumber|string|false|none|none|
|Type|string|false|none|none|

<h2 id="tocS_Quote">Quote</h2>
<!-- backwards compatibility -->
<a id="schemaquote"></a>
<a id="schema_Quote"></a>
<a id="tocSquote"></a>
<a id="tocsquote"></a>

```json
{
  "AirlineCharges": {
    "Fixed": [
      {
        "Amount": 0,
        "Currency": "string",
        "Description": "string",
        "IsPaid": true,
        "IsPrimary": true,
        "SemanticsCode": "string",
        "SemanticsVendorType": "string",
        "StartDateLocal": "string",
        "Vendor": "string",
        "VendorChargeCode": "string"
      }
    ],
    "Percent": [
      {
        "Amount": 0,
        "Currency": "string",
        "Description": "string",
        "IsPaid": true,
        "IsPrimary": true,
        "SemanticsCode": "string",
        "SemanticsVendorType": "string",
        "StartDateLocal": "string",
        "Vendor": "string",
        "VendorChargeCode": "string"
      }
    ],
    "Rate": [
      {
        "Amount": 0,
        "Currency": "string",
        "Description": "string",
        "IsPaid": true,
        "IsPrimary": true,
        "NumUnits": 0,
        "PerUnit": "string",
        "SemanticsCode": "string",
        "SemanticsVendorType": "string",
        "StartDateLocal": "string",
        "Vendor": "string",
        "VendorChargeCode": "string"
      }
    ],
    "RateWithAllowance": [
      {
        "AllowanceAmount": 0,
        "AllowanceIsUnlimited": true,
        "AllowanceNumUnits": 0,
        "AllowanceUnit": "string",
        "Amount": 0,
        "Currency": "string",
        "Description": "string",
        "IsPaid": true,
        "IsPrimary": true,
        "NumUnits": 0,
        "PerUnit": "string",
        "SemanticsCode": "string",
        "SemanticsVendorType": "string",
        "StartDateLocal": "string",
        "Vendor": "string",
        "VendorChargeCode": "string"
      }
    ]
  },
  "BaseFare": 0,
  "BaseFareCurrency": "string",
  "BaseFareNuc": 0,
  "BaseFareNucCurrency": "string",
  "DateCreatedUtc": "string",
  "DateModifiedUtc": "string",
  "Endorsements": "string",
  "IssueByDate": "string",
  "TotalFare": 0,
  "TotalFareCurrency": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|AirlineCharges|[ChargeDetail](#schemachargedetail)|false|none|none|
|BaseFare|number|false|none|none|
|BaseFareCurrency|string|false|none|none|
|BaseFareNuc|number|false|none|none|
|BaseFareNucCurrency|string|false|none|none|
|DateCreatedUtc|string|false|none|none|
|DateModifiedUtc|string|false|none|none|
|Endorsements|string|false|none|none|
|IssueByDate|string|false|none|none|
|TotalFare|number|false|none|none|
|TotalFareCurrency|string|false|none|none|

<h2 id="tocS_Rail">Rail</h2>
<!-- backwards compatibility -->
<a id="schemarail"></a>
<a id="schema_Rail"></a>
<a id="tocSrail"></a>
<a id="tocsrail"></a>

```json
{
  "Amenities": "string",
  "Cabin": "string",
  "CancellationNumber": "string",
  "CarbonEmissionLbs": 0,
  "CarbonModel": 0,
  "Charges": {
    "Fixed": [
      {
        "Amount": 0,
        "Currency": "string",
        "Description": "string",
        "IsPaid": true,
        "IsPrimary": true,
        "SemanticsCode": "string",
        "SemanticsVendorType": "string",
        "StartDateLocal": "string",
        "Vendor": "string",
        "VendorChargeCode": "string"
      }
    ],
    "Percent": [
      {
        "Amount": 0,
        "Currency": "string",
        "Description": "string",
        "IsPaid": true,
        "IsPrimary": true,
        "SemanticsCode": "string",
        "SemanticsVendorType": "string",
        "StartDateLocal": "string",
        "Vendor": "string",
        "VendorChargeCode": "string"
      }
    ],
    "Rate": [
      {
        "Amount": 0,
        "Currency": "string",
        "Description": "string",
        "IsPaid": true,
        "IsPrimary": true,
        "NumUnits": 0,
        "PerUnit": "string",
        "SemanticsCode": "string",
        "SemanticsVendorType": "string",
        "StartDateLocal": "string",
        "Vendor": "string",
        "VendorChargeCode": "string"
      }
    ],
    "RateWithAllowance": [
      {
        "AllowanceAmount": 0,
        "AllowanceIsUnlimited": true,
        "AllowanceNumUnits": 0,
        "AllowanceUnit": "string",
        "Amount": 0,
        "Currency": "string",
        "Description": "string",
        "IsPaid": true,
        "IsPrimary": true,
        "NumUnits": 0,
        "PerUnit": "string",
        "SemanticsCode": "string",
        "SemanticsVendorType": "string",
        "StartDateLocal": "string",
        "Vendor": "string",
        "VendorChargeCode": "string"
      }
    ]
  },
  "ClassOfService": "string",
  "ConfirmationNumber": "string",
  "Currency": "string",
  "DateCancelledUtc": "string",
  "DateCreatedUtc": "string",
  "DateModifiedUtc": "string",
  "DiscountCode": "string",
  "Duration": 0,
  "ETicket": "string",
  "EndCity": "string",
  "EndCityCode": "string",
  "EndCountry": "string",
  "EndDateLocal": "string",
  "EndDateUtc": "string",
  "EndLatitude": 0,
  "EndLongitude": 0,
  "EndPlatform": "string",
  "EndRailStation": "string",
  "EndRailStationName": "string",
  "EndState": "string",
  "FrequentTravelerId": "string",
  "IsPreferredVendor": 0,
  "IsUpgradeAllowed": true,
  "LegId": 0,
  "Meals": "string",
  "Miles": 0,
  "Notes": "string",
  "NumPersons": 0,
  "NumStops": 0,
  "OperatedByTrainNumber": "string",
  "OperatedByVendor": "string",
  "RateCode": "string",
  "Remarks": {
    "TripLinkRemarks": [
      {
        "TripLinkRemark": [
          {
            "Text": "string"
          }
        ]
      }
    ]
  },
  "RouteRestrictCode": "string",
  "Seats": [
    {
      "Amenities": "string",
      "BerthPosition": "string",
      "Deck": "string",
      "FacingForward": "string",
      "FareSpaceComfort": "string",
      "PassengerRph": 0,
      "SeatNumber": "string",
      "SeatPosition": "string",
      "SeatType": "string",
      "SpaceType": "string",
      "Status": "string",
      "WagonNumber": "string",
      "WagonType": "string"
    }
  ],
  "SpecialInstructions": "string",
  "StartCity": "string",
  "StartCityCode": "string",
  "StartCountry": "string",
  "StartDateLocal": "string",
  "StartDateUtc": "string",
  "StartLatitude": 0,
  "StartLongitude": 0,
  "StartPlatform": "string",
  "StartRailStation": "string",
  "StartRailStationName": "string",
  "StartState": "string",
  "Status": "string",
  "TimeZone": "string",
  "TimeZoneId": 0,
  "TotalRate": 0,
  "TrainNumber": "string",
  "TrainTypeCode": "string",
  "TrainTypeName": "string",
  "TransportMode": "string",
  "UpgradedDateTime": "string",
  "Vendor": "string",
  "VendorFlags": "string",
  "VendorName": "string",
  "WagonNumber": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Amenities|string|false|none|none|
|Cabin|string|false|none|none|
|CancellationNumber|string|false|none|none|
|CarbonEmissionLbs|number|false|none|none|
|CarbonModel|integer|false|none|none|
|Charges|[ChargeDetail](#schemachargedetail)|false|none|none|
|ClassOfService|string|false|none|none|
|ConfirmationNumber|string|false|none|none|
|Currency|string|false|none|none|
|DateCancelledUtc|string|false|none|none|
|DateCreatedUtc|string|false|none|none|
|DateModifiedUtc|string|false|none|none|
|DiscountCode|string|false|none|none|
|Duration|integer|false|none|none|
|ETicket|string|false|none|none|
|EndCity|string|false|none|none|
|EndCityCode|string|false|none|none|
|EndCountry|string|false|none|none|
|EndDateLocal|string|false|none|none|
|EndDateUtc|string|false|none|none|
|EndLatitude|number|false|none|none|
|EndLongitude|number|false|none|none|
|EndPlatform|string|false|none|none|
|EndRailStation|string|false|none|none|
|EndRailStationName|string|false|none|none|
|EndState|string|false|none|none|
|FrequentTravelerId|string|false|none|none|
|IsPreferredVendor|integer|false|none|none|
|IsUpgradeAllowed|boolean|false|none|none|
|LegId|integer|false|none|none|
|Meals|string|false|none|none|
|Miles|integer|false|none|none|
|Notes|string|false|none|none|
|NumPersons|integer|false|none|none|
|NumStops|integer|false|none|none|
|OperatedByTrainNumber|string|false|none|none|
|OperatedByVendor|string|false|none|none|
|RateCode|string|false|none|none|
|Remarks|[Remarks](#schemaremarks)|false|none|none|
|RouteRestrictCode|string|false|none|none|
|Seats|[[RailSeat](#schemarailseat)]|false|none|none|
|SpecialInstructions|string|false|none|none|
|StartCity|string|false|none|none|
|StartCityCode|string|false|none|none|
|StartCountry|string|false|none|none|
|StartDateLocal|string|true|none|none|
|StartDateUtc|string|false|none|none|
|StartLatitude|number|false|none|none|
|StartLongitude|number|false|none|none|
|StartPlatform|string|false|none|none|
|StartRailStation|string|false|none|none|
|StartRailStationName|string|false|none|none|
|StartState|string|false|none|none|
|Status|string|false|none|none|
|TimeZone|string|false|none|none|
|TimeZoneId|integer|false|none|none|
|TotalRate|number|false|none|none|
|TrainNumber|string|false|none|none|
|TrainTypeCode|string|false|none|none|
|TrainTypeName|string|false|none|none|
|TransportMode|string|false|none|none|
|UpgradedDateTime|string|false|none|none|
|Vendor|string|false|none|none|
|VendorFlags|string|false|none|none|
|VendorName|string|false|none|none|
|WagonNumber|string|false|none|none|

<h2 id="tocS_RailAdjustment">RailAdjustment</h2>
<!-- backwards compatibility -->
<a id="schemarailadjustment"></a>
<a id="schema_RailAdjustment"></a>
<a id="tocSrailadjustment"></a>
<a id="tocsrailadjustment"></a>

```json
{
  "AdjustmentDateTime": "string",
  "AdjustmentDateTimeUTC": "string",
  "AdjustmentType": "string",
  "DateCreatedUtc": "string",
  "DateModifiedUtc": "string",
  "RailCharges": {
    "Fixed": [
      {
        "Amount": 0,
        "Currency": "string",
        "Description": "string",
        "IsPaid": true,
        "IsPrimary": true,
        "SemanticsCode": "string",
        "SemanticsVendorType": "string",
        "StartDateLocal": "string",
        "Vendor": "string",
        "VendorChargeCode": "string"
      }
    ],
    "Percent": [
      {
        "Amount": 0,
        "Currency": "string",
        "Description": "string",
        "IsPaid": true,
        "IsPrimary": true,
        "SemanticsCode": "string",
        "SemanticsVendorType": "string",
        "StartDateLocal": "string",
        "Vendor": "string",
        "VendorChargeCode": "string"
      }
    ],
    "Rate": [
      {
        "Amount": 0,
        "Currency": "string",
        "Description": "string",
        "IsPaid": true,
        "IsPrimary": true,
        "NumUnits": 0,
        "PerUnit": "string",
        "SemanticsCode": "string",
        "SemanticsVendorType": "string",
        "StartDateLocal": "string",
        "Vendor": "string",
        "VendorChargeCode": "string"
      }
    ],
    "RateWithAllowance": [
      {
        "AllowanceAmount": 0,
        "AllowanceIsUnlimited": true,
        "AllowanceNumUnits": 0,
        "AllowanceUnit": "string",
        "Amount": 0,
        "Currency": "string",
        "Description": "string",
        "IsPaid": true,
        "IsPrimary": true,
        "NumUnits": 0,
        "PerUnit": "string",
        "SemanticsCode": "string",
        "SemanticsVendorType": "string",
        "StartDateLocal": "string",
        "Vendor": "string",
        "VendorChargeCode": "string"
      }
    ]
  },
  "Taxes": [
    {
      "TaxAmount": 0,
      "TaxAuthority": "string",
      "TaxName": "string",
      "TaxRate": 0,
      "TaxType": "string"
    }
  ],
  "TicketDocumentIdentifier": "string",
  "TotalAdjustment": 0,
  "TotalAdjustmentCurrency": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|AdjustmentDateTime|string|false|none|none|
|AdjustmentDateTimeUTC|string|false|none|none|
|AdjustmentType|string|false|none|none|
|DateCreatedUtc|string|false|none|none|
|DateModifiedUtc|string|false|none|none|
|RailCharges|[ChargeDetail](#schemachargedetail)|false|none|none|
|Taxes|[[Tax](#schematax)]|false|none|none|
|TicketDocumentIdentifier|string|false|none|none|
|TotalAdjustment|number|false|none|none|
|TotalAdjustmentCurrency|string|false|none|none|

<h2 id="tocS_RailPayment">RailPayment</h2>
<!-- backwards compatibility -->
<a id="schemarailpayment"></a>
<a id="schema_RailPayment"></a>
<a id="tocSrailpayment"></a>
<a id="tocsrailpayment"></a>

```json
{
  "BaseFare": 0,
  "BaseFareCurrency": "string",
  "DateCreatedUtc": "string",
  "DateModifiedUtc": "string",
  "IncludesVAT": true,
  "IssueByDate": "string",
  "IssueDateTime": "string",
  "IssueDateTimeUTC": "string",
  "RailCharges": {
    "Fixed": [
      {
        "Amount": 0,
        "Currency": "string",
        "Description": "string",
        "IsPaid": true,
        "IsPrimary": true,
        "SemanticsCode": "string",
        "SemanticsVendorType": "string",
        "StartDateLocal": "string",
        "Vendor": "string",
        "VendorChargeCode": "string"
      }
    ],
    "Percent": [
      {
        "Amount": 0,
        "Currency": "string",
        "Description": "string",
        "IsPaid": true,
        "IsPrimary": true,
        "SemanticsCode": "string",
        "SemanticsVendorType": "string",
        "StartDateLocal": "string",
        "Vendor": "string",
        "VendorChargeCode": "string"
      }
    ],
    "Rate": [
      {
        "Amount": 0,
        "Currency": "string",
        "Description": "string",
        "IsPaid": true,
        "IsPrimary": true,
        "NumUnits": 0,
        "PerUnit": "string",
        "SemanticsCode": "string",
        "SemanticsVendorType": "string",
        "StartDateLocal": "string",
        "Vendor": "string",
        "VendorChargeCode": "string"
      }
    ],
    "RateWithAllowance": [
      {
        "AllowanceAmount": 0,
        "AllowanceIsUnlimited": true,
        "AllowanceNumUnits": 0,
        "AllowanceUnit": "string",
        "Amount": 0,
        "Currency": "string",
        "Description": "string",
        "IsPaid": true,
        "IsPrimary": true,
        "NumUnits": 0,
        "PerUnit": "string",
        "SemanticsCode": "string",
        "SemanticsVendorType": "string",
        "StartDateLocal": "string",
        "Vendor": "string",
        "VendorChargeCode": "string"
      }
    ]
  },
  "TaxInvoice": true,
  "Taxes": [
    {
      "TaxAmount": 0,
      "TaxAuthority": "string",
      "TaxName": "string",
      "TaxRate": 0,
      "TaxType": "string"
    }
  ],
  "TicketDocumentIdentifier": "string",
  "TicketType": "string",
  "TotalFare": 0,
  "TotalFareCurrency": "string",
  "vatApplicable": true
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|BaseFare|number|false|none|none|
|BaseFareCurrency|string|false|none|none|
|DateCreatedUtc|string|false|none|none|
|DateModifiedUtc|string|false|none|none|
|IncludesVAT|boolean|false|none|none|
|IssueByDate|string|false|none|none|
|IssueDateTime|string|false|none|none|
|IssueDateTimeUTC|string|false|none|none|
|RailCharges|[ChargeDetail](#schemachargedetail)|false|none|none|
|TaxInvoice|boolean|false|none|none|
|Taxes|[[Tax](#schematax)]|false|none|none|
|TicketDocumentIdentifier|string|false|none|none|
|TicketType|string|false|none|none|
|TotalFare|number|false|none|none|
|TotalFareCurrency|string|false|none|none|
|vatApplicable|boolean|false|none|none|

<h2 id="tocS_RailProgram">RailProgram</h2>
<!-- backwards compatibility -->
<a id="schemarailprogram"></a>
<a id="schema_RailProgram"></a>
<a id="tocSrailprogram"></a>
<a id="tocsrailprogram"></a>

```json
{
  "Description": "string",
  "DiscountProgramExpirationDate": "string",
  "DiscountProgramType": "string",
  "ProgramNumber": "string",
  "Status": "string",
  "StatusExpirationDate": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Description|string|false|none|none|
|DiscountProgramExpirationDate|string|false|none|none|
|DiscountProgramType|string|false|none|none|
|ProgramNumber|string|false|none|none|
|Status|string|false|none|none|
|StatusExpirationDate|string|false|none|none|

<h2 id="tocS_RailSeat">RailSeat</h2>
<!-- backwards compatibility -->
<a id="schemarailseat"></a>
<a id="schema_RailSeat"></a>
<a id="tocSrailseat"></a>
<a id="tocsrailseat"></a>

```json
{
  "Amenities": "string",
  "BerthPosition": "string",
  "Deck": "string",
  "FacingForward": "string",
  "FareSpaceComfort": "string",
  "PassengerRph": 0,
  "SeatNumber": "string",
  "SeatPosition": "string",
  "SeatType": "string",
  "SpaceType": "string",
  "Status": "string",
  "WagonNumber": "string",
  "WagonType": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Amenities|string|false|none|none|
|BerthPosition|string|false|none|none|
|Deck|string|false|none|none|
|FacingForward|string|false|none|none|
|FareSpaceComfort|string|false|none|none|
|PassengerRph|integer|false|none|none|
|SeatNumber|string|false|none|none|
|SeatPosition|string|false|none|none|
|SeatType|string|false|none|none|
|SpaceType|string|false|none|none|
|Status|string|false|none|none|
|WagonNumber|string|false|none|none|
|WagonType|string|false|none|none|

<h2 id="tocS_Rate">Rate</h2>
<!-- backwards compatibility -->
<a id="schemarate"></a>
<a id="schema_Rate"></a>
<a id="tocSrate"></a>
<a id="tocsrate"></a>

```json
{
  "Amount": 0,
  "Currency": "string",
  "Description": "string",
  "IsPaid": true,
  "IsPrimary": true,
  "NumUnits": 0,
  "PerUnit": "string",
  "SemanticsCode": "string",
  "SemanticsVendorType": "string",
  "StartDateLocal": "string",
  "Vendor": "string",
  "VendorChargeCode": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Amount|number|false|none|none|
|Currency|string|false|none|none|
|Description|string|false|none|none|
|IsPaid|boolean|false|none|none|
|IsPrimary|boolean|false|none|none|
|NumUnits|number|false|none|none|
|PerUnit|string|false|none|none|
|SemanticsCode|string|false|none|none|
|SemanticsVendorType|string|false|none|none|
|StartDateLocal|string|false|none|none|
|Vendor|string|false|none|none|
|VendorChargeCode|string|false|none|none|

<h2 id="tocS_RateWithAllowance">RateWithAllowance</h2>
<!-- backwards compatibility -->
<a id="schemaratewithallowance"></a>
<a id="schema_RateWithAllowance"></a>
<a id="tocSratewithallowance"></a>
<a id="tocsratewithallowance"></a>

```json
{
  "AllowanceAmount": 0,
  "AllowanceIsUnlimited": true,
  "AllowanceNumUnits": 0,
  "AllowanceUnit": "string",
  "Amount": 0,
  "Currency": "string",
  "Description": "string",
  "IsPaid": true,
  "IsPrimary": true,
  "NumUnits": 0,
  "PerUnit": "string",
  "SemanticsCode": "string",
  "SemanticsVendorType": "string",
  "StartDateLocal": "string",
  "Vendor": "string",
  "VendorChargeCode": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|AllowanceAmount|number|false|none|none|
|AllowanceIsUnlimited|boolean|false|none|none|
|AllowanceNumUnits|number|false|none|none|
|AllowanceUnit|string|false|none|none|
|Amount|number|false|none|none|
|Currency|string|false|none|none|
|Description|string|false|none|none|
|IsPaid|boolean|false|none|none|
|IsPrimary|boolean|false|none|none|
|NumUnits|number|false|none|none|
|PerUnit|string|false|none|none|
|SemanticsCode|string|false|none|none|
|SemanticsVendorType|string|false|none|none|
|StartDateLocal|string|false|none|none|
|Vendor|string|false|none|none|
|VendorChargeCode|string|false|none|none|

<h2 id="tocS_Remarks">Remarks</h2>
<!-- backwards compatibility -->
<a id="schemaremarks"></a>
<a id="schema_Remarks"></a>
<a id="tocSremarks"></a>
<a id="tocsremarks"></a>

```json
{
  "TripLinkRemarks": [
    {
      "TripLinkRemark": [
        {
          "Text": "string"
        }
      ]
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|TripLinkRemarks|[[TripLinkRemarks](#schematriplinkremarks)]|false|none|none|

<h2 id="tocS_Ride">Ride</h2>
<!-- backwards compatibility -->
<a id="schemaride"></a>
<a id="schema_Ride"></a>
<a id="tocSride"></a>
<a id="tocsride"></a>

```json
{
  "CancellationNumber": "string",
  "CancellationPolicy": "string",
  "Charges": {
    "Fixed": [
      {
        "Amount": 0,
        "Currency": "string",
        "Description": "string",
        "IsPaid": true,
        "IsPrimary": true,
        "SemanticsCode": "string",
        "SemanticsVendorType": "string",
        "StartDateLocal": "string",
        "Vendor": "string",
        "VendorChargeCode": "string"
      }
    ],
    "Percent": [
      {
        "Amount": 0,
        "Currency": "string",
        "Description": "string",
        "IsPaid": true,
        "IsPrimary": true,
        "SemanticsCode": "string",
        "SemanticsVendorType": "string",
        "StartDateLocal": "string",
        "Vendor": "string",
        "VendorChargeCode": "string"
      }
    ],
    "Rate": [
      {
        "Amount": 0,
        "Currency": "string",
        "Description": "string",
        "IsPaid": true,
        "IsPrimary": true,
        "NumUnits": 0,
        "PerUnit": "string",
        "SemanticsCode": "string",
        "SemanticsVendorType": "string",
        "StartDateLocal": "string",
        "Vendor": "string",
        "VendorChargeCode": "string"
      }
    ],
    "RateWithAllowance": [
      {
        "AllowanceAmount": 0,
        "AllowanceIsUnlimited": true,
        "AllowanceNumUnits": 0,
        "AllowanceUnit": "string",
        "Amount": 0,
        "Currency": "string",
        "Description": "string",
        "IsPaid": true,
        "IsPrimary": true,
        "NumUnits": 0,
        "PerUnit": "string",
        "SemanticsCode": "string",
        "SemanticsVendorType": "string",
        "StartDateLocal": "string",
        "Vendor": "string",
        "VendorChargeCode": "string"
      }
    ]
  },
  "ConfirmationNumber": "string",
  "Currency": "string",
  "DateCancelledUtc": "string",
  "DateCreatedUtc": "string",
  "DateModifiedUtc": "string",
  "DropoffInstructions": "string",
  "Duration": 0,
  "EndAddress": "string",
  "EndAddress2": "string",
  "EndCity": "string",
  "EndCityCode": "string",
  "EndCountry": "string",
  "EndDateLocal": "string",
  "EndDateUtc": "string",
  "EndLatitude": 0,
  "EndLocationCode": "string",
  "EndLongitude": 0,
  "EndPostalCode": "string",
  "EndState": "string",
  "IsGhostCard": true,
  "IsPreferredVendor": 0,
  "IsUpgradeAllowed": true,
  "MeetingInstructions": "string",
  "Miles": 0,
  "Name": "string",
  "Notes": "string",
  "NumPersons": 0,
  "NumberOfHours": 0,
  "OperatedByVendorName": "string",
  "PassiveCityCode": "string",
  "PhoneNumber": "string",
  "PickupInstructions": "string",
  "ProviderFeedback": "string",
  "Rate": 0,
  "RateDescription": "string",
  "RateNotes": "string",
  "RateType": "string",
  "Remarks": {
    "TripLinkRemarks": [
      {
        "TripLinkRemark": [
          {
            "Text": "string"
          }
        ]
      }
    ]
  },
  "ReservationId": "string",
  "SpecialInstructions": "string",
  "StartAddress": "string",
  "StartAddress2": "string",
  "StartCity": "string",
  "StartCityCode": "string",
  "StartCountry": "string",
  "StartDateLocal": "string",
  "StartDateUtc": "string",
  "StartLatitude": 0,
  "StartLocation": "string",
  "StartLocationCode": "string",
  "StartLocationName": "string",
  "StartLongitude": 0,
  "StartPostalCode": "string",
  "StartState": "string",
  "TimeZone": "string",
  "TimeZoneId": 0,
  "TotalRate": 0,
  "UpgradedDateTime": "string",
  "Vendor": "string",
  "VendorFlags": "string",
  "VendorName": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|CancellationNumber|string|false|none|none|
|CancellationPolicy|string|false|none|none|
|Charges|[ChargeDetail](#schemachargedetail)|false|none|none|
|ConfirmationNumber|string|false|none|none|
|Currency|string|false|none|none|
|DateCancelledUtc|string|false|none|none|
|DateCreatedUtc|string|false|none|none|
|DateModifiedUtc|string|false|none|none|
|DropoffInstructions|string|false|none|none|
|Duration|integer|false|none|none|
|EndAddress|string|false|none|none|
|EndAddress2|string|false|none|none|
|EndCity|string|false|none|none|
|EndCityCode|string|false|none|none|
|EndCountry|string|false|none|none|
|EndDateLocal|string|false|none|none|
|EndDateUtc|string|false|none|none|
|EndLatitude|number|false|none|none|
|EndLocationCode|string|false|none|none|
|EndLongitude|number|false|none|none|
|EndPostalCode|string|false|none|none|
|EndState|string|false|none|none|
|IsGhostCard|boolean|false|none|none|
|IsPreferredVendor|integer|false|none|none|
|IsUpgradeAllowed|boolean|false|none|none|
|MeetingInstructions|string|false|none|none|
|Miles|integer|false|none|none|
|Name|string|false|none|none|
|Notes|string|false|none|none|
|NumPersons|integer|false|none|none|
|NumberOfHours|number|false|none|none|
|OperatedByVendorName|string|false|none|none|
|PassiveCityCode|string|false|none|none|
|PhoneNumber|string|false|none|none|
|PickupInstructions|string|false|none|none|
|ProviderFeedback|string|false|none|none|
|Rate|number|false|none|none|
|RateDescription|string|false|none|none|
|RateNotes|string|false|none|none|
|RateType|string|false|none|none|
|Remarks|[Remarks](#schemaremarks)|false|none|none|
|ReservationId|string|false|none|none|
|SpecialInstructions|string|false|none|none|
|StartAddress|string|false|none|none|
|StartAddress2|string|false|none|none|
|StartCity|string|false|none|none|
|StartCityCode|string|false|none|none|
|StartCountry|string|false|none|none|
|StartDateLocal|string|false|none|none|
|StartDateUtc|string|false|none|none|
|StartLatitude|number|false|none|none|
|StartLocation|string|false|none|none|
|StartLocationCode|string|false|none|none|
|StartLocationName|string|false|none|none|
|StartLongitude|number|false|none|none|
|StartPostalCode|string|false|none|none|
|StartState|string|false|none|none|
|TimeZone|string|false|none|none|
|TimeZoneId|integer|false|none|none|
|TotalRate|number|false|none|none|
|UpgradedDateTime|string|false|none|none|
|Vendor|string|false|none|none|
|VendorFlags|string|false|none|none|
|VendorName|string|false|none|none|

<h2 id="tocS_RuleViolation">RuleViolation</h2>
<!-- backwards compatibility -->
<a id="schemaruleviolation"></a>
<a id="schema_RuleViolation"></a>
<a id="tocSruleviolation"></a>
<a id="tocsruleviolation"></a>

```json
{
  "CompanyReasonCode": "string",
  "CompanyRuleText": "string",
  "ViolationReasonCode": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|CompanyReasonCode|string|false|none|none|
|CompanyRuleText|string|false|none|none|
|ViolationReasonCode|integer|false|none|none|

<h2 id="tocS_Segment">Segment</h2>
<!-- backwards compatibility -->
<a id="schemasegment"></a>
<a id="schema_Segment"></a>
<a id="tocSsegment"></a>
<a id="tocssegment"></a>

```json
{
  "Air": [
    {
      "AircraftCode": "string",
      "Bags": "string",
      "Cabin": "string",
      "CancellationNumber": "string",
      "CancellationPolicy": "string",
      "CarbonEmissionLbs": 0,
      "CarbonModel": 0,
      "Charges": {
        "Fixed": [
          {
            "Amount": 0,
            "Currency": "string",
            "Description": "string",
            "IsPaid": true,
            "IsPrimary": true,
            "SemanticsCode": "string",
            "SemanticsVendorType": "string",
            "StartDateLocal": "string",
            "Vendor": "string",
            "VendorChargeCode": "string"
          }
        ],
        "Percent": [
          {
            "Amount": 0,
            "Currency": "string",
            "Description": "string",
            "IsPaid": true,
            "IsPrimary": true,
            "SemanticsCode": "string",
            "SemanticsVendorType": "string",
            "StartDateLocal": "string",
            "Vendor": "string",
            "VendorChargeCode": "string"
          }
        ],
        "Rate": [
          {
            "Amount": 0,
            "Currency": "string",
            "Description": "string",
            "IsPaid": true,
            "IsPrimary": true,
            "NumUnits": 0,
            "PerUnit": "string",
            "SemanticsCode": "string",
            "SemanticsVendorType": "string",
            "StartDateLocal": "string",
            "Vendor": "string",
            "VendorChargeCode": "string"
          }
        ],
        "RateWithAllowance": [
          {
            "AllowanceAmount": 0,
            "AllowanceIsUnlimited": true,
            "AllowanceNumUnits": 0,
            "AllowanceUnit": "string",
            "Amount": 0,
            "Currency": "string",
            "Description": "string",
            "IsPaid": true,
            "IsPrimary": true,
            "NumUnits": 0,
            "PerUnit": "string",
            "SemanticsCode": "string",
            "SemanticsVendorType": "string",
            "StartDateLocal": "string",
            "Vendor": "string",
            "VendorChargeCode": "string"
          }
        ]
      },
      "CheckedBaggage": "string",
      "ClassOfService": "string",
      "ConfirmationNumber": "string",
      "DateCancelledUtc": "string",
      "DateCreatedUtc": "string",
      "DateModifiedUtc": "string",
      "Duration": 0,
      "ETicket": "string",
      "EndCityCode": "string",
      "EndDateLocal": "string",
      "EndDateUtc": "string",
      "EndGate": "string",
      "EndTerminal": "string",
      "FlightNumber": "string",
      "FrequentTravelerId": "string",
      "IsOpenSegment": true,
      "IsPreferredVendor": 0,
      "IsUpgradeAllowed": true,
      "LegId": 0,
      "Meals": "string",
      "Miles": 0,
      "Notes": "string",
      "NumStops": 0,
      "OpenSegment": "string",
      "OperatedByFlightNumber": "string",
      "OperatedByVendor": "string",
      "OperatedByVendorName": "string",
      "Remarks": {
        "TripLinkRemarks": [
          {
            "TripLinkRemark": [
              {
                "Text": "string"
              }
            ]
          }
        ]
      },
      "RuleViolations": [
        {
          "CompanyReasonCode": "string",
          "CompanyRuleText": "string",
          "ViolationReasonCode": 0
        }
      ],
      "Seats": [
        {
          "PassengerRph": 0,
          "SeatNumber": "string",
          "Status": "string"
        }
      ],
      "Services": "string",
      "SpecialInstructions": "string",
      "StartCityCode": "string",
      "StartDateLocal": "string",
      "StartDateUtc": "string",
      "StartGate": "string",
      "StartTerminal": "string",
      "Status": "string",
      "TimeZone": "string",
      "TimeZoneId": 0,
      "UpgradedDateTime": "string",
      "Vendor": "string",
      "VendorFlags": "string",
      "VendorName": "string"
    }
  ],
  "Car": [
    {
      "AirCondition": "string",
      "Body": "string",
      "CancellationNumber": "string",
      "Charges": {
        "Fixed": [
          {
            "Amount": 0,
            "Currency": "string",
            "Description": "string",
            "IsPaid": true,
            "IsPrimary": true,
            "SemanticsCode": "string",
            "SemanticsVendorType": "string",
            "StartDateLocal": "string",
            "Vendor": "string",
            "VendorChargeCode": "string"
          }
        ],
        "Percent": [
          {
            "Amount": 0,
            "Currency": "string",
            "Description": "string",
            "IsPaid": true,
            "IsPrimary": true,
            "SemanticsCode": "string",
            "SemanticsVendorType": "string",
            "StartDateLocal": "string",
            "Vendor": "string",
            "VendorChargeCode": "string"
          }
        ],
        "Rate": [
          {
            "Amount": 0,
            "Currency": "string",
            "Description": "string",
            "IsPaid": true,
            "IsPrimary": true,
            "NumUnits": 0,
            "PerUnit": "string",
            "SemanticsCode": "string",
            "SemanticsVendorType": "string",
            "StartDateLocal": "string",
            "Vendor": "string",
            "VendorChargeCode": "string"
          }
        ],
        "RateWithAllowance": [
          {
            "AllowanceAmount": 0,
            "AllowanceIsUnlimited": true,
            "AllowanceNumUnits": 0,
            "AllowanceUnit": "string",
            "Amount": 0,
            "Currency": "string",
            "Description": "string",
            "IsPaid": true,
            "IsPrimary": true,
            "NumUnits": 0,
            "PerUnit": "string",
            "SemanticsCode": "string",
            "SemanticsVendorType": "string",
            "StartDateLocal": "string",
            "Vendor": "string",
            "VendorChargeCode": "string"
          }
        ]
      },
      "Class": "string",
      "ConfirmationNumber": "string",
      "Currency": "string",
      "DailyRate": 0,
      "DateCancelledUtc": "string",
      "DateCreatedUtc": "string",
      "DateModifiedUtc": "string",
      "DiscountCode": "string",
      "DropoffCollectionAddress1": "string",
      "DropoffCollectionAddressType": "string",
      "DropoffCollectionCategory": "string",
      "DropoffCollectionCity": "string",
      "DropoffCollectionCityCode": "string",
      "DropoffCollectionCountry": "string",
      "DropoffCollectionLatitude": "string",
      "DropoffCollectionLongitude": "string",
      "DropoffCollectionNumber": "string",
      "DropoffCollectionPhoneNumber": "string",
      "DropoffCollectionPostalCode": "string",
      "DropoffCollectionState": "string",
      "EndAddress": "string",
      "EndAddress2": "string",
      "EndCity": "string",
      "EndCityCode": "string",
      "EndCloseTime": "string",
      "EndCountry": "string",
      "EndDateLocal": "string",
      "EndDateUtc": "string",
      "EndLatitude": 0,
      "EndLongitude": 0,
      "EndOpenTime": "string",
      "EndPhoneNumber": "string",
      "EndPostalCode": "string",
      "EndState": "string",
      "IsGhostCard": true,
      "IsPreferredVendor": 0,
      "IsUpgradeAllowed": true,
      "Notes": "string",
      "NumCars": 0,
      "NumPersons": 0,
      "PhoneNumber": "string",
      "PickupDeliveryAddress1": "string",
      "PickupDeliveryAddressType": "string",
      "PickupDeliveryCategory": "string",
      "PickupDeliveryCity": "string",
      "PickupDeliveryCityCode": "string",
      "PickupDeliveryCountry": "string",
      "PickupDeliveryLatitude": "string",
      "PickupDeliveryLongitude": "string",
      "PickupDeliveryNumber": "string",
      "PickupDeliveryPhoneNumber": "string",
      "PickupDeliveryPostalCode": "string",
      "PickupDeliveryState": "string",
      "RateCode": "string",
      "RateType": "string",
      "Remarks": {
        "TripLinkRemarks": [
          {
            "TripLinkRemark": [
              {
                "Text": "string"
              }
            ]
          }
        ]
      },
      "SpecialEquipment": "string",
      "SpecialInstructions": "string",
      "StartAddress": "string",
      "StartAddress2": "string",
      "StartCity": "string",
      "StartCityCode": "string",
      "StartCloseTime": "string",
      "StartCountry": "string",
      "StartDateLocal": "string",
      "StartDateUtc": "string",
      "StartLatitude": 0,
      "StartLocation": "string",
      "StartLongitude": 0,
      "StartOpenTime": "string",
      "StartPostalCode": "string",
      "StartState": "string",
      "Status": "string",
      "TimeZone": "string",
      "TimeZoneId": 0,
      "TotalRate": 0,
      "Transmission": "string",
      "UpgradedDateTime": "string",
      "Vendor": "string",
      "VendorFlags": "string",
      "VendorName": "string"
    }
  ],
  "Dining": [
    {
      "CancellationNumber": "string",
      "Charges": {
        "Fixed": [
          {
            "Amount": 0,
            "Currency": "string",
            "Description": "string",
            "IsPaid": true,
            "IsPrimary": true,
            "SemanticsCode": "string",
            "SemanticsVendorType": "string",
            "StartDateLocal": "string",
            "Vendor": "string",
            "VendorChargeCode": "string"
          }
        ],
        "Percent": [
          {
            "Amount": 0,
            "Currency": "string",
            "Description": "string",
            "IsPaid": true,
            "IsPrimary": true,
            "SemanticsCode": "string",
            "SemanticsVendorType": "string",
            "StartDateLocal": "string",
            "Vendor": "string",
            "VendorChargeCode": "string"
          }
        ],
        "Rate": [
          {
            "Amount": 0,
            "Currency": "string",
            "Description": "string",
            "IsPaid": true,
            "IsPrimary": true,
            "NumUnits": 0,
            "PerUnit": "string",
            "SemanticsCode": "string",
            "SemanticsVendorType": "string",
            "StartDateLocal": "string",
            "Vendor": "string",
            "VendorChargeCode": "string"
          }
        ],
        "RateWithAllowance": [
          {
            "AllowanceAmount": 0,
            "AllowanceIsUnlimited": true,
            "AllowanceNumUnits": 0,
            "AllowanceUnit": "string",
            "Amount": 0,
            "Currency": "string",
            "Description": "string",
            "IsPaid": true,
            "IsPrimary": true,
            "NumUnits": 0,
            "PerUnit": "string",
            "SemanticsCode": "string",
            "SemanticsVendorType": "string",
            "StartDateLocal": "string",
            "Vendor": "string",
            "VendorChargeCode": "string"
          }
        ]
      },
      "ConfirmationNumber": "string",
      "DateCancelledUtc": "string",
      "DateCreatedUtc": "string",
      "DateModifiedUtc": "string",
      "EndDateLocal": "string",
      "EndDateUtc": "string",
      "FrequentTravelerId": "string",
      "IsPreferredVendor": 0,
      "IsUpgradeAllowed": true,
      "Name": "string",
      "Notes": "string",
      "NumPersons": 0,
      "PhoneNumber": "string",
      "Remarks": {
        "TripLinkRemarks": [
          {
            "TripLinkRemark": [
              {
                "Text": "string"
              }
            ]
          }
        ]
      },
      "ReservationId": "string",
      "StartAddress": "string",
      "StartAddress2": "string",
      "StartCity": "string",
      "StartCountry": "string",
      "StartDateLocal": "string",
      "StartDateUtc": "string",
      "StartLatitude": 0,
      "StartLongitude": 0,
      "StartPostalCode": "string",
      "StartState": "string",
      "Status": "string",
      "TimeZone": "string",
      "TimeZoneId": 0,
      "UpgradedDateTime": "string",
      "Vendor": "string",
      "VendorFlags": "string",
      "VendorName": "string"
    }
  ],
  "Hotel": [
    {
      "Breakfast": true,
      "CancellationNumber": "string",
      "CancellationPolicy": "string",
      "Charges": {
        "Fixed": [
          {
            "Amount": 0,
            "Currency": "string",
            "Description": "string",
            "IsPaid": true,
            "IsPrimary": true,
            "SemanticsCode": "string",
            "SemanticsVendorType": "string",
            "StartDateLocal": "string",
            "Vendor": "string",
            "VendorChargeCode": "string"
          }
        ],
        "Percent": [
          {
            "Amount": 0,
            "Currency": "string",
            "Description": "string",
            "IsPaid": true,
            "IsPrimary": true,
            "SemanticsCode": "string",
            "SemanticsVendorType": "string",
            "StartDateLocal": "string",
            "Vendor": "string",
            "VendorChargeCode": "string"
          }
        ],
        "Rate": [
          {
            "Amount": 0,
            "Currency": "string",
            "Description": "string",
            "IsPaid": true,
            "IsPrimary": true,
            "NumUnits": 0,
            "PerUnit": "string",
            "SemanticsCode": "string",
            "SemanticsVendorType": "string",
            "StartDateLocal": "string",
            "Vendor": "string",
            "VendorChargeCode": "string"
          }
        ],
        "RateWithAllowance": [
          {
            "AllowanceAmount": 0,
            "AllowanceIsUnlimited": true,
            "AllowanceNumUnits": 0,
            "AllowanceUnit": "string",
            "Amount": 0,
            "Currency": "string",
            "Description": "string",
            "IsPaid": true,
            "IsPrimary": true,
            "NumUnits": 0,
            "PerUnit": "string",
            "SemanticsCode": "string",
            "SemanticsVendorType": "string",
            "StartDateLocal": "string",
            "Vendor": "string",
            "VendorChargeCode": "string"
          }
        ]
      },
      "CheckinTime": "string",
      "CheckoutTime": "string",
      "ConfirmationNumber": "string",
      "Currency": "string",
      "DailyRate": 0,
      "DateCancelledUtc": "string",
      "DateCreatedUtc": "string",
      "DateModifiedUtc": "string",
      "DirectBill": true,
      "DiscountCode": "string",
      "Email": "string",
      "EndDateLocal": "string",
      "EndDateUtc": "string",
      "EquipmentCode": "string",
      "FaxNumber": "string",
      "FrequentTravelerId": "string",
      "HotelPropertyId": "string",
      "IncludedCustomAmenities": "string",
      "IsGhostCard": true,
      "IsPreferredVendor": 0,
      "IsUpgradeAllowed": true,
      "ModificationCode": "string",
      "Name": "string",
      "Notes": "string",
      "NumPersons": 0,
      "NumRooms": 0,
      "Parking": true,
      "PartnerMembershipId": "string",
      "PassiveType": "string",
      "PhoneNumber": "string",
      "RateAccess": "string",
      "RateCode": "string",
      "RateType": "string",
      "Remarks": {
        "TripLinkRemarks": [
          {
            "TripLinkRemark": [
              {
                "Text": "string"
              }
            ]
          }
        ]
      },
      "RoomDescription": "string",
      "RoomType": "string",
      "SpecialInstructions": "string",
      "StartAddress": "string",
      "StartAddress2": "string",
      "StartCity": "string",
      "StartCityCode": "string",
      "StartCountry": "string",
      "StartDateLocal": "string",
      "StartDateUtc": "string",
      "StartLatitude": 0,
      "StartLongitude": 0,
      "StartPostalCode": "string",
      "StartState": "string",
      "Status": "string",
      "TimeZone": "string",
      "TimeZoneId": 0,
      "TotalRate": 0,
      "UpgradedDateTime": "string",
      "Vendor": "string",
      "VendorFlags": "string",
      "VendorName": "string",
      "Wifi": true
    }
  ],
  "Parking": [
    {
      "CancellationNumber": "string",
      "Charges": {
        "Fixed": [
          {
            "Amount": 0,
            "Currency": "string",
            "Description": "string",
            "IsPaid": true,
            "IsPrimary": true,
            "SemanticsCode": "string",
            "SemanticsVendorType": "string",
            "StartDateLocal": "string",
            "Vendor": "string",
            "VendorChargeCode": "string"
          }
        ],
        "Percent": [
          {
            "Amount": 0,
            "Currency": "string",
            "Description": "string",
            "IsPaid": true,
            "IsPrimary": true,
            "SemanticsCode": "string",
            "SemanticsVendorType": "string",
            "StartDateLocal": "string",
            "Vendor": "string",
            "VendorChargeCode": "string"
          }
        ],
        "Rate": [
          {
            "Amount": 0,
            "Currency": "string",
            "Description": "string",
            "IsPaid": true,
            "IsPrimary": true,
            "NumUnits": 0,
            "PerUnit": "string",
            "SemanticsCode": "string",
            "SemanticsVendorType": "string",
            "StartDateLocal": "string",
            "Vendor": "string",
            "VendorChargeCode": "string"
          }
        ],
        "RateWithAllowance": [
          {
            "AllowanceAmount": 0,
            "AllowanceIsUnlimited": true,
            "AllowanceNumUnits": 0,
            "AllowanceUnit": "string",
            "Amount": 0,
            "Currency": "string",
            "Description": "string",
            "IsPaid": true,
            "IsPrimary": true,
            "NumUnits": 0,
            "PerUnit": "string",
            "SemanticsCode": "string",
            "SemanticsVendorType": "string",
            "StartDateLocal": "string",
            "Vendor": "string",
            "VendorChargeCode": "string"
          }
        ]
      },
      "ClassOfService": "string",
      "ConfirmationNumber": "string",
      "Currency": "string",
      "DateCancelledUtc": "string",
      "DateCreatedUtc": "string",
      "DateModifiedUtc": "string",
      "EndDateLocal": "string",
      "EndDateUtc": "string",
      "FrequentTravelerId": "string",
      "IsPreferredVendor": 0,
      "IsUpgradeAllowed": true,
      "Name": "string",
      "Notes": "string",
      "OperatedByVendor": "string",
      "ParkingLocationId": "string",
      "PhoneNumber": "string",
      "Pin": "string",
      "RateCode": "string",
      "Remarks": {
        "TripLinkRemarks": [
          {
            "TripLinkRemark": [
              {
                "Text": "string"
              }
            ]
          }
        ]
      },
      "StartAddress": "string",
      "StartAddress2": "string",
      "StartCity": "string",
      "StartCityCode": "string",
      "StartCountry": "string",
      "StartDateLocal": "string",
      "StartDateUtc": "string",
      "StartLocation": "string",
      "StartPostalCode": "string",
      "StartState": "string",
      "Status": "string",
      "TimeZone": "string",
      "TimeZoneId": 0,
      "TotalRate": 0,
      "UpgradedDateTime": "string",
      "Vendor": "string",
      "VendorFlags": "string",
      "VendorName": "string"
    }
  ],
  "Rail": [
    {
      "Amenities": "string",
      "Cabin": "string",
      "CancellationNumber": "string",
      "CarbonEmissionLbs": 0,
      "CarbonModel": 0,
      "Charges": {
        "Fixed": [
          {
            "Amount": 0,
            "Currency": "string",
            "Description": "string",
            "IsPaid": true,
            "IsPrimary": true,
            "SemanticsCode": "string",
            "SemanticsVendorType": "string",
            "StartDateLocal": "string",
            "Vendor": "string",
            "VendorChargeCode": "string"
          }
        ],
        "Percent": [
          {
            "Amount": 0,
            "Currency": "string",
            "Description": "string",
            "IsPaid": true,
            "IsPrimary": true,
            "SemanticsCode": "string",
            "SemanticsVendorType": "string",
            "StartDateLocal": "string",
            "Vendor": "string",
            "VendorChargeCode": "string"
          }
        ],
        "Rate": [
          {
            "Amount": 0,
            "Currency": "string",
            "Description": "string",
            "IsPaid": true,
            "IsPrimary": true,
            "NumUnits": 0,
            "PerUnit": "string",
            "SemanticsCode": "string",
            "SemanticsVendorType": "string",
            "StartDateLocal": "string",
            "Vendor": "string",
            "VendorChargeCode": "string"
          }
        ],
        "RateWithAllowance": [
          {
            "AllowanceAmount": 0,
            "AllowanceIsUnlimited": true,
            "AllowanceNumUnits": 0,
            "AllowanceUnit": "string",
            "Amount": 0,
            "Currency": "string",
            "Description": "string",
            "IsPaid": true,
            "IsPrimary": true,
            "NumUnits": 0,
            "PerUnit": "string",
            "SemanticsCode": "string",
            "SemanticsVendorType": "string",
            "StartDateLocal": "string",
            "Vendor": "string",
            "VendorChargeCode": "string"
          }
        ]
      },
      "ClassOfService": "string",
      "ConfirmationNumber": "string",
      "Currency": "string",
      "DateCancelledUtc": "string",
      "DateCreatedUtc": "string",
      "DateModifiedUtc": "string",
      "DiscountCode": "string",
      "Duration": 0,
      "ETicket": "string",
      "EndCity": "string",
      "EndCityCode": "string",
      "EndCountry": "string",
      "EndDateLocal": "string",
      "EndDateUtc": "string",
      "EndLatitude": 0,
      "EndLongitude": 0,
      "EndPlatform": "string",
      "EndRailStation": "string",
      "EndRailStationName": "string",
      "EndState": "string",
      "FrequentTravelerId": "string",
      "IsPreferredVendor": 0,
      "IsUpgradeAllowed": true,
      "LegId": 0,
      "Meals": "string",
      "Miles": 0,
      "Notes": "string",
      "NumPersons": 0,
      "NumStops": 0,
      "OperatedByTrainNumber": "string",
      "OperatedByVendor": "string",
      "RateCode": "string",
      "Remarks": {
        "TripLinkRemarks": [
          {
            "TripLinkRemark": [
              {
                "Text": "string"
              }
            ]
          }
        ]
      },
      "RouteRestrictCode": "string",
      "Seats": [
        {
          "Amenities": "string",
          "BerthPosition": "string",
          "Deck": "string",
          "FacingForward": "string",
          "FareSpaceComfort": "string",
          "PassengerRph": 0,
          "SeatNumber": "string",
          "SeatPosition": "string",
          "SeatType": "string",
          "SpaceType": "string",
          "Status": "string",
          "WagonNumber": "string",
          "WagonType": "string"
        }
      ],
      "SpecialInstructions": "string",
      "StartCity": "string",
      "StartCityCode": "string",
      "StartCountry": "string",
      "StartDateLocal": "string",
      "StartDateUtc": "string",
      "StartLatitude": 0,
      "StartLongitude": 0,
      "StartPlatform": "string",
      "StartRailStation": "string",
      "StartRailStationName": "string",
      "StartState": "string",
      "Status": "string",
      "TimeZone": "string",
      "TimeZoneId": 0,
      "TotalRate": 0,
      "TrainNumber": "string",
      "TrainTypeCode": "string",
      "TrainTypeName": "string",
      "TransportMode": "string",
      "UpgradedDateTime": "string",
      "Vendor": "string",
      "VendorFlags": "string",
      "VendorName": "string",
      "WagonNumber": "string"
    }
  ],
  "Ride": [
    {
      "CancellationNumber": "string",
      "CancellationPolicy": "string",
      "Charges": {
        "Fixed": [
          {
            "Amount": 0,
            "Currency": "string",
            "Description": "string",
            "IsPaid": true,
            "IsPrimary": true,
            "SemanticsCode": "string",
            "SemanticsVendorType": "string",
            "StartDateLocal": "string",
            "Vendor": "string",
            "VendorChargeCode": "string"
          }
        ],
        "Percent": [
          {
            "Amount": 0,
            "Currency": "string",
            "Description": "string",
            "IsPaid": true,
            "IsPrimary": true,
            "SemanticsCode": "string",
            "SemanticsVendorType": "string",
            "StartDateLocal": "string",
            "Vendor": "string",
            "VendorChargeCode": "string"
          }
        ],
        "Rate": [
          {
            "Amount": 0,
            "Currency": "string",
            "Description": "string",
            "IsPaid": true,
            "IsPrimary": true,
            "NumUnits": 0,
            "PerUnit": "string",
            "SemanticsCode": "string",
            "SemanticsVendorType": "string",
            "StartDateLocal": "string",
            "Vendor": "string",
            "VendorChargeCode": "string"
          }
        ],
        "RateWithAllowance": [
          {
            "AllowanceAmount": 0,
            "AllowanceIsUnlimited": true,
            "AllowanceNumUnits": 0,
            "AllowanceUnit": "string",
            "Amount": 0,
            "Currency": "string",
            "Description": "string",
            "IsPaid": true,
            "IsPrimary": true,
            "NumUnits": 0,
            "PerUnit": "string",
            "SemanticsCode": "string",
            "SemanticsVendorType": "string",
            "StartDateLocal": "string",
            "Vendor": "string",
            "VendorChargeCode": "string"
          }
        ]
      },
      "ConfirmationNumber": "string",
      "Currency": "string",
      "DateCancelledUtc": "string",
      "DateCreatedUtc": "string",
      "DateModifiedUtc": "string",
      "DropoffInstructions": "string",
      "Duration": 0,
      "EndAddress": "string",
      "EndAddress2": "string",
      "EndCity": "string",
      "EndCityCode": "string",
      "EndCountry": "string",
      "EndDateLocal": "string",
      "EndDateUtc": "string",
      "EndLatitude": 0,
      "EndLocationCode": "string",
      "EndLongitude": 0,
      "EndPostalCode": "string",
      "EndState": "string",
      "IsGhostCard": true,
      "IsPreferredVendor": 0,
      "IsUpgradeAllowed": true,
      "MeetingInstructions": "string",
      "Miles": 0,
      "Name": "string",
      "Notes": "string",
      "NumPersons": 0,
      "NumberOfHours": 0,
      "OperatedByVendorName": "string",
      "PassiveCityCode": "string",
      "PhoneNumber": "string",
      "PickupInstructions": "string",
      "ProviderFeedback": "string",
      "Rate": 0,
      "RateDescription": "string",
      "RateNotes": "string",
      "RateType": "string",
      "Remarks": {
        "TripLinkRemarks": [
          {
            "TripLinkRemark": [
              {
                "Text": "string"
              }
            ]
          }
        ]
      },
      "ReservationId": "string",
      "SpecialInstructions": "string",
      "StartAddress": "string",
      "StartAddress2": "string",
      "StartCity": "string",
      "StartCityCode": "string",
      "StartCountry": "string",
      "StartDateLocal": "string",
      "StartDateUtc": "string",
      "StartLatitude": 0,
      "StartLocation": "string",
      "StartLocationCode": "string",
      "StartLocationName": "string",
      "StartLongitude": 0,
      "StartPostalCode": "string",
      "StartState": "string",
      "TimeZone": "string",
      "TimeZoneId": 0,
      "TotalRate": 0,
      "UpgradedDateTime": "string",
      "Vendor": "string",
      "VendorFlags": "string",
      "VendorName": "string"
    }
  ],
  "Travel": [
    {
      "CancellationNumber": "string",
      "Charges": {
        "Fixed": [
          {
            "Amount": 0,
            "Currency": "string",
            "Description": "string",
            "IsPaid": true,
            "IsPrimary": true,
            "SemanticsCode": "string",
            "SemanticsVendorType": "string",
            "StartDateLocal": "string",
            "Vendor": "string",
            "VendorChargeCode": "string"
          }
        ],
        "Percent": [
          {
            "Amount": 0,
            "Currency": "string",
            "Description": "string",
            "IsPaid": true,
            "IsPrimary": true,
            "SemanticsCode": "string",
            "SemanticsVendorType": "string",
            "StartDateLocal": "string",
            "Vendor": "string",
            "VendorChargeCode": "string"
          }
        ],
        "Rate": [
          {
            "Amount": 0,
            "Currency": "string",
            "Description": "string",
            "IsPaid": true,
            "IsPrimary": true,
            "NumUnits": 0,
            "PerUnit": "string",
            "SemanticsCode": "string",
            "SemanticsVendorType": "string",
            "StartDateLocal": "string",
            "Vendor": "string",
            "VendorChargeCode": "string"
          }
        ],
        "RateWithAllowance": [
          {
            "AllowanceAmount": 0,
            "AllowanceIsUnlimited": true,
            "AllowanceNumUnits": 0,
            "AllowanceUnit": "string",
            "Amount": 0,
            "Currency": "string",
            "Description": "string",
            "IsPaid": true,
            "IsPrimary": true,
            "NumUnits": 0,
            "PerUnit": "string",
            "SemanticsCode": "string",
            "SemanticsVendorType": "string",
            "StartDateLocal": "string",
            "Vendor": "string",
            "VendorChargeCode": "string"
          }
        ]
      },
      "ConfirmationNumber": "string",
      "Currency": "string",
      "DailyRate": 0,
      "DateCancelledUtc": "string",
      "DateCreatedUtc": "string",
      "DateModifiedUtc": "string",
      "EndAddress": "string",
      "EndAddress2": "string",
      "EndCity": "string",
      "EndCityCode": "string",
      "EndCountry": "string",
      "EndDateLocal": "string",
      "EndDateUtc": "string",
      "EndLatitude": 0,
      "EndLocation": "string",
      "EndLongitude": 0,
      "EndPostalCode": "string",
      "EndState": "string",
      "IsGhostCard": true,
      "Notes": "string",
      "NumPersons": 0,
      "PhoneNumber": "string",
      "Remarks": {
        "TripLinkRemarks": [
          {
            "TripLinkRemark": [
              {
                "Text": "string"
              }
            ]
          }
        ]
      },
      "SpecialInstructions": "string",
      "StartAddress": "string",
      "StartAddress2": "string",
      "StartCity": "string",
      "StartCityCode": "string",
      "StartCountry": "string",
      "StartDateLocal": "string",
      "StartDateUtc": "string",
      "StartLatitude": 0,
      "StartLocation": "string",
      "StartLongitude": 0,
      "StartPostalCode": "string",
      "StartState": "string",
      "Status": "string",
      "TimeZone": "string",
      "TimeZoneId": 0,
      "TotalRate": 0,
      "TransportMode": "string",
      "Vendor": "string",
      "VendorName": "string"
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Air|[[Air](#schemaair)]|false|none|none|
|Car|[[Car](#schemacar)]|false|none|none|
|Dining|[[Dining](#schemadining)]|false|none|none|
|Hotel|[[Hotel](#schemahotel)]|false|none|none|
|Parking|[[Parking](#schemaparking)]|false|none|none|
|Rail|[[Rail](#schemarail)]|false|none|none|
|Ride|[[Ride](#schemaride)]|false|none|none|
|Travel|[[Travel](#schematravel)]|false|none|none|

<h2 id="tocS_SegmentOptionFlightType">SegmentOptionFlightType</h2>
<!-- backwards compatibility -->
<a id="schemasegmentoptionflighttype"></a>
<a id="schema_SegmentOptionFlightType"></a>
<a id="tocSsegmentoptionflighttype"></a>
<a id="tocssegmentoptionflighttype"></a>

```json
{
  "ArrAirp": "string",
  "Cabin": "string",
  "Carrier": "string",
  "DepAirp": "string",
  "FlightNum": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|ArrAirp|string|false|none|none|
|Cabin|string|false|none|none|
|Carrier|string|false|none|none|
|DepAirp|string|false|none|none|
|FlightNum|string|false|none|none|

<h2 id="tocS_SegmentOptionItem">SegmentOptionItem</h2>
<!-- backwards compatibility -->
<a id="schemasegmentoptionitem"></a>
<a id="schema_SegmentOptionItem"></a>
<a id="tocSsegmentoptionitem"></a>
<a id="tocssegmentoptionitem"></a>

```json
{
  "Flight": [
    {
      "ArrAirp": "string",
      "Cabin": "string",
      "Carrier": "string",
      "DepAirp": "string",
      "FlightNum": "string"
    }
  ],
  "SegmentIndex": "string",
  "StatusCode": "string",
  "TimeStamp": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Flight|[[SegmentOptionFlightType](#schemasegmentoptionflighttype)]|false|none|none|
|SegmentIndex|string|false|none|none|
|StatusCode|string|false|none|none|
|TimeStamp|string|false|none|none|

<h2 id="tocS_Tax">Tax</h2>
<!-- backwards compatibility -->
<a id="schematax"></a>
<a id="schema_Tax"></a>
<a id="tocStax"></a>
<a id="tocstax"></a>

```json
{
  "TaxAmount": 0,
  "TaxAuthority": "string",
  "TaxName": "string",
  "TaxRate": 0,
  "TaxType": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|TaxAmount|number|false|none|none|
|TaxAuthority|string|false|none|none|
|TaxName|string|false|none|none|
|TaxRate|number|false|none|none|
|TaxType|string|false|none|none|

<h2 id="tocS_Travel">Travel</h2>
<!-- backwards compatibility -->
<a id="schematravel"></a>
<a id="schema_Travel"></a>
<a id="tocStravel"></a>
<a id="tocstravel"></a>

```json
{
  "CancellationNumber": "string",
  "Charges": {
    "Fixed": [
      {
        "Amount": 0,
        "Currency": "string",
        "Description": "string",
        "IsPaid": true,
        "IsPrimary": true,
        "SemanticsCode": "string",
        "SemanticsVendorType": "string",
        "StartDateLocal": "string",
        "Vendor": "string",
        "VendorChargeCode": "string"
      }
    ],
    "Percent": [
      {
        "Amount": 0,
        "Currency": "string",
        "Description": "string",
        "IsPaid": true,
        "IsPrimary": true,
        "SemanticsCode": "string",
        "SemanticsVendorType": "string",
        "StartDateLocal": "string",
        "Vendor": "string",
        "VendorChargeCode": "string"
      }
    ],
    "Rate": [
      {
        "Amount": 0,
        "Currency": "string",
        "Description": "string",
        "IsPaid": true,
        "IsPrimary": true,
        "NumUnits": 0,
        "PerUnit": "string",
        "SemanticsCode": "string",
        "SemanticsVendorType": "string",
        "StartDateLocal": "string",
        "Vendor": "string",
        "VendorChargeCode": "string"
      }
    ],
    "RateWithAllowance": [
      {
        "AllowanceAmount": 0,
        "AllowanceIsUnlimited": true,
        "AllowanceNumUnits": 0,
        "AllowanceUnit": "string",
        "Amount": 0,
        "Currency": "string",
        "Description": "string",
        "IsPaid": true,
        "IsPrimary": true,
        "NumUnits": 0,
        "PerUnit": "string",
        "SemanticsCode": "string",
        "SemanticsVendorType": "string",
        "StartDateLocal": "string",
        "Vendor": "string",
        "VendorChargeCode": "string"
      }
    ]
  },
  "ConfirmationNumber": "string",
  "Currency": "string",
  "DailyRate": 0,
  "DateCancelledUtc": "string",
  "DateCreatedUtc": "string",
  "DateModifiedUtc": "string",
  "EndAddress": "string",
  "EndAddress2": "string",
  "EndCity": "string",
  "EndCityCode": "string",
  "EndCountry": "string",
  "EndDateLocal": "string",
  "EndDateUtc": "string",
  "EndLatitude": 0,
  "EndLocation": "string",
  "EndLongitude": 0,
  "EndPostalCode": "string",
  "EndState": "string",
  "IsGhostCard": true,
  "Notes": "string",
  "NumPersons": 0,
  "PhoneNumber": "string",
  "Remarks": {
    "TripLinkRemarks": [
      {
        "TripLinkRemark": [
          {
            "Text": "string"
          }
        ]
      }
    ]
  },
  "SpecialInstructions": "string",
  "StartAddress": "string",
  "StartAddress2": "string",
  "StartCity": "string",
  "StartCityCode": "string",
  "StartCountry": "string",
  "StartDateLocal": "string",
  "StartDateUtc": "string",
  "StartLatitude": 0,
  "StartLocation": "string",
  "StartLongitude": 0,
  "StartPostalCode": "string",
  "StartState": "string",
  "Status": "string",
  "TimeZone": "string",
  "TimeZoneId": 0,
  "TotalRate": 0,
  "TransportMode": "string",
  "Vendor": "string",
  "VendorName": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|CancellationNumber|string|false|none|none|
|Charges|[ChargeDetail](#schemachargedetail)|false|none|none|
|ConfirmationNumber|string|false|none|none|
|Currency|string|false|none|none|
|DailyRate|number|false|none|none|
|DateCancelledUtc|string|false|none|none|
|DateCreatedUtc|string|false|none|none|
|DateModifiedUtc|string|false|none|none|
|EndAddress|string|false|none|none|
|EndAddress2|string|false|none|none|
|EndCity|string|false|none|none|
|EndCityCode|string|false|none|none|
|EndCountry|string|false|none|none|
|EndDateLocal|string|false|none|none|
|EndDateUtc|string|false|none|none|
|EndLatitude|number|false|none|none|
|EndLocation|string|false|none|none|
|EndLongitude|number|false|none|none|
|EndPostalCode|string|false|none|none|
|EndState|string|false|none|none|
|IsGhostCard|boolean|false|none|none|
|Notes|string|false|none|none|
|NumPersons|integer|false|none|none|
|PhoneNumber|string|false|none|none|
|Remarks|[Remarks](#schemaremarks)|false|none|none|
|SpecialInstructions|string|false|none|none|
|StartAddress|string|false|none|none|
|StartAddress2|string|false|none|none|
|StartCity|string|false|none|none|
|StartCityCode|string|false|none|none|
|StartCountry|string|false|none|none|
|StartDateLocal|string|true|none|none|
|StartDateUtc|string|false|none|none|
|StartLatitude|number|false|none|none|
|StartLocation|string|false|none|none|
|StartLongitude|number|false|none|none|
|StartPostalCode|string|false|none|none|
|StartState|string|false|none|none|
|Status|string|false|none|none|
|TimeZone|string|false|none|none|
|TimeZoneId|integer|false|none|none|
|TotalRate|number|false|none|none|
|TransportMode|string|false|none|none|
|Vendor|string|false|none|none|
|VendorName|string|false|none|none|

<h2 id="tocS_TripLinkRemark">TripLinkRemark</h2>
<!-- backwards compatibility -->
<a id="schematriplinkremark"></a>
<a id="schema_TripLinkRemark"></a>
<a id="tocStriplinkremark"></a>
<a id="tocstriplinkremark"></a>

```json
{
  "Text": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Text|string|false|none|none|

<h2 id="tocS_TripLinkRemarks">TripLinkRemarks</h2>
<!-- backwards compatibility -->
<a id="schematriplinkremarks"></a>
<a id="schema_TripLinkRemarks"></a>
<a id="tocStriplinkremarks"></a>
<a id="tocstriplinkremarks"></a>

```json
{
  "TripLinkRemark": [
    {
      "Text": "string"
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|TripLinkRemark|[[TripLinkRemark](#schematriplinkremark)]|false|none|none|

<h2 id="tocS_WaitListSegments">WaitListSegments</h2>
<!-- backwards compatibility -->
<a id="schemawaitlistsegments"></a>
<a id="schema_WaitListSegments"></a>
<a id="tocSwaitlistsegments"></a>
<a id="tocswaitlistsegments"></a>

```json
{
  "SegmentOption": [
    {
      "Flight": [
        {
          "ArrAirp": "string",
          "Cabin": "string",
          "Carrier": "string",
          "DepAirp": "string",
          "FlightNum": "string"
        }
      ],
      "SegmentIndex": "string",
      "StatusCode": "string",
      "TimeStamp": "string"
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|SegmentOption|[[SegmentOptionItem](#schemasegmentoptionitem)]|false|none|none|

<h2 id="tocS_Warning">Warning</h2>
<!-- backwards compatibility -->
<a id="schemawarning"></a>
<a id="schema_Warning"></a>
<a id="tocSwarning"></a>
<a id="tocswarning"></a>

```json
{
  "Code": [
    "string"
  ],
  "Text": [
    "string"
  ],
  "Type": [
    "string"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Code|[string]|false|none|none|
|Text|[string]|false|none|none|
|Type|[string]|false|none|none|

<h2 id="tocS_WebAddressData">WebAddressData</h2>
<!-- backwards compatibility -->
<a id="schemawebaddressdata"></a>
<a id="schema_WebAddressData"></a>
<a id="tocSwebaddressdata"></a>
<a id="tocswebaddressdata"></a>

```json
{
  "Description": "string",
  "Format": "string",
  "PassengerRPH": 0,
  "Type": "string",
  "WebAddress": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Description|string|false|none|none|
|Format|string|false|none|none|
|PassengerRPH|integer|false|none|none|
|Type|string|false|none|none|
|WebAddress|string|false|none|none|

<h2 id="tocS_model.ErrorAPIResponse">model.ErrorAPIResponse</h2>
<!-- backwards compatibility -->
<a id="schemamodel.errorapiresponse"></a>
<a id="schema_model.ErrorAPIResponse"></a>
<a id="tocSmodel.errorapiresponse"></a>
<a id="tocsmodel.errorapiresponse"></a>

```json
{
  "errors": [
    {
      "errorCode": "string",
      "errorMessage": "string",
      "errors": [
        {}
      ]
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|errors|[[model.ExternalErrorObject](#schemamodel.externalerrorobject)]|false|none|none|

<h2 id="tocS_model.ExternalErrorObject">model.ExternalErrorObject</h2>
<!-- backwards compatibility -->
<a id="schemamodel.externalerrorobject"></a>
<a id="schema_model.ExternalErrorObject"></a>
<a id="tocSmodel.externalerrorobject"></a>
<a id="tocsmodel.externalerrorobject"></a>

```json
{
  "errorCode": "string",
  "errorMessage": "string",
  "errors": [
    {
      "errorCode": "string",
      "errorMessage": "string",
      "errors": []
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|errorCode|string|false|none|none|
|errorMessage|string|false|none|none|
|errors|[[model.ExternalErrorObject](#schemamodel.externalerrorobject)]|false|none|none|

