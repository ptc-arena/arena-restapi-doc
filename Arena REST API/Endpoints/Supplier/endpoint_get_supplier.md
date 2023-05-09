# GET Supplier (Profile)


/suppliers/&lt;GUID&gt;

Returns a  object with a given GUID.

## Request Header

| Name | Value | Description |
|  --- |  --- |  --- | 
| arena_session_id |   | unique ID for session obtained from login |
| content\-type | application/json |   |

## Response Codes

| Code | Description |
|  --- |  --- | 
| 200 | Success |
| 400 | Failure |

## Response Header

| Name | Value | Description |
|  --- |  --- |  --- | 
| Content\-Length | number | number of characters in response |
| Content\-Type | application/json | content type of response |
| Date | date | today's date and time |
| Server | ArenaSolutions |   |
| X\-Arena\-Next\-Request\-Limit\-Reset  | date | the scheduled time for resetting of the count |
| X\-Arena\-Requests\-Remaining  | number | how many calls left |

## Sample Response Body
Get a supplier with a given GUID



/suppliers/&lt;GUID&gt;

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
   "supplierId":"atrisksupplier",
   "website":"www.zombo.com"
}
```
Request with bad GUID

```
{
  "status": 400,
  "errors": [
    {
      "code": 3011,
      "message": "The guid \"0I2L4CLLIZISBUDUIUI4\" is not valid."
    }
  ]
}
```
