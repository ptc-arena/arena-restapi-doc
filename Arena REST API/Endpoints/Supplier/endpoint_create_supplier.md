# POST Supplier Create


/suppliers

Creates a new  object. 

NOTES:

* The values you specify for attributes must match the attribute types specified in the workspace. For example, when specifying a value for a predefined list, the value must be one of the allowed values.

* Number values must appear in quotation marks.

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content\-type<br> | application/json<br> |   |

## Sample Request Body
```
{
   "accountNumber":"1",
   "additionalAttributes":[
      {
         "guid":"I0K3MU330HYGZI1K9K72",
         "value":"Yes"
      },
      {
         "guid":"K2M5OW552J0I1K3MBM9V",
         "value":"Good results. Good shipping."
      },
      {
         "guid":"J1L4NV441IZH0J2LAL8A",
         "value":"Persephone"
      },
      {
         "guid":"HZJ2LT22ZGXFYH0J8J6T",
         "value":"2019-01-01T06:59:59Z"
      },
      {
         "guid":"9RBUZPLU2XEWFYHUORWT",
         "value":"2018-03-21T22:40:10Z"
      }
   ],
   "addresses":[
      {
         "primary":true,
         "address":{
            "label":"HQ",
            "address1":"1 Main St",
            "address2":"Box 100",
            "city":"San Bruno",
            "state":"California",
            "province":"",
            "postalCode":"94066",
            "Country/Region":"United States"
         }
      }
   ],
   "approvalStatus":"approved",
   "description":"Board house",
   "name":"The Board Room",
   "phoneNumbers":[
      {
         "number":"111-111-1111",
         "label":"Main"
      },
      {
         "number":"111-111-1110",
         "label":"Fax"
      }
   ],
   "supplierId":"theboardroominc",
   "website":"www.zombo.com"
}
```
## Response Codes

| Code<br> | Description<br> |
|  --- |  --- | 
| 201<br> | Success<br> |
| 400<br> | Failure<br> |

## Response Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| Content\-Length<br> | number<br> | number of characters in response<br> |
| Content\-Type<br> | application/json<br> | content type of response<br> |
| Date<br> | date<br> | today's date and time<br> |
| Server<br> | ArenaSolutions<br> |   |
| X\-Arena\-Next\-Request\-Limit\-Reset<br> | date<br> | the scheduled time for resetting of the count<br> |
| X\-Arena\-Requests\-Remaining<br> | number<br> | how many calls left<br> |

## Sample Response Body
Create a new supplier



/suppliers

```
{
   "accountNumber":"1",
   "additionalAttributes":[
      {
         "apiName":"custom1411225",
         "fieldType":"DATE",
         "guid":"HZJ2LT22ZGXFYH0J8J6T",
         "name":"Re-Evaluate On",
         "value":"2019-01-01T07:59:59Z"
      },
      {
         "apiName":"custom1411226",
         "fieldType":"FIXED_DROP_DOWN",
         "guid":"I0K3MU330HYGZI1K9K72",
         "name":"At-Risk Supplier?",
         "value":"Yes"
      },
      {
         "apiName":"custom1411227",
         "fieldType":"DROP_DOWN",
         "guid":"J1L4NV441IZH0J2LAL8A",
         "name":"Product Line",
         "value":"Persephone"
      },
      {
         "apiName":"custom1411228",
         "fieldType":"MULTI_LINE_TEXT",
         "guid":"K2M5OW552J0I1K3MBM9V",
         "name":"Internal reviews",
         "value":"Good results. Good shipping."
      }
   ],
   "addresses":[
      {
         "address":{
            "address1":"1 Main St",
            "address2":"Box 100",
            "city":"San Bruno",
            "Country/Region":"United States",
            "label":"hq",
            "postalCode":"94066",
            "province":null,
            "state":"CALIFORNIA"
         },
         "primary":true
      }
   ],
   "approvalStatus":"approved",
   "creationDateTime":"2018-04-27T00:18:52Z",
   "creator":{
      "email":"hwalker@everyroadgps.com",
      "fullName":"Heidi Walker"
   },
   "description":"Board house",
   "guid":"UCWFY6FFCTCI1K3B82OC",
   "name":"The Board Room",
   "phoneNumbers":[
      {
         "comment":null,
         "extension":null,
         "label":"Main",
         "number":"111-111-1111"
      },
      {
         "comment":null,
         "extension":null,
         "label":"Fax",
         "number":"111-111-1110"
      }
   ],
   "supplierId": "theboardroominc",
   "website":"www.zombo.com"
}
```
Request with invalid Country/Region or state

```
{  
    "status":400,
    "errors":[  
        {  
            "code":3045,
            "message":"The Country/Region or state is invalid for the supplier address."
        }
    ]
}
```
