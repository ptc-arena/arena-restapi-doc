# PUT Supplier Update


/suppliers/&lt;GUID&gt;

Updates the metadata of a  with a given GUID. To update values for additional attributes, first retrieve the GUID of each attribute using the GET Supplier Item endpoint.  Updated values must be valid for the attribute.

## Request Header

| Name | Value | Description |
|  --- |  --- |  --- | 
| arena_session_id |   | unique ID for session obtained from login |
| content\-type | application/json |   |

## Set Null

| Name | Value | Description |
|  --- |  --- |  --- | 
| setnull |   | Append the URL with setnull=true to set supplierId, accountNumber, description, or website to null. Attributes must be included within the request body and set to null. Insert setnull after the query string, represented by a ?, after the GUID |

## Sample Request Body
PUT /suppliers/&lt;GUID&gt;

```
{
   "additionalAttributes":[
      {
         "guid":"I0K3MU330HYGZI1K9K72",
         "value":"No"
      },
      {
         "guid":"K2M5OW552J0I1K3MBM9V",
         "value":"Failed to meet deadline."
      },
      {
         "guid":"J1L4NV441IZH0J2LAL8A",
         "value":"Hades"
      },
      {
         "guid":"HZJ2LT22ZGXFYH0J8J6T",
         "value":"2019-02-01T06:59:59Z"
      }
   ],
   "accountNumber":"1",
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
      },
      {
         "primary":false,
         "address":{
            "label":"sales",
            "address1":"1313 Mockingbird Lane",
            "city":"Smalltown",
            "state":"New York",
            "province":"",
            "postalCode":"01234",
            "Country/Region":"United States"
         }
      }
   ],
   "approvalStatus":"approved",
   "description":"Full service board house",
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
   "supplierId": "theboardroomllc",
   "website":"www.zombo.com"
}
```
PUT /suppliers/&lt;GUID&gt;?setnull=true

```
{
    "supplierId": null
}
```
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
Update the metadata for a supplier



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
         "value":"2019-02-01T06:59:59Z"
      },
      {
         "apiName":"custom1411226",
         "fieldType":"FIXED_DROP_DOWN",
         "guid":"I0K3MU330HYGZI1K9K72",
         "name":"At-Risk Supplier?",
         "value":"No"
      },
      {
         "apiName":"custom1411227",
         "fieldType":"DROP_DOWN",
         "guid":"J1L4NV441IZH0J2LAL8A",
         "name":"Product Line",
         "value":"Hades"
      },
      {
         "apiName":"custom1411228",
         "fieldType":"MULTI_LINE_TEXT",
         "guid":"K2M5OW552J0I1K3MBM9V",
         "name":"Internal reviews",
         "value":"Failed to meet deadline."
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
      },
      {
         "address":{
            "label":"sales",
            "address1":"1313 Mockingbird Lane",
            "city":"Smalltown",
            "state":"New York",
            "province":"",
            "postalCode":"01234",
            "Country/Region":"United States"
         },
         "primary":false
      }
   ],
   "approvalStatus":"approved",
   "creationDateTime":"2018-04-27T00:18:52Z",
   "creator":{
      "email":"hwalker@everyroadgps.com",
      "fullName":"Heidi Walker"
   },
   "description":"Full service board house",
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
   "supplierId":"theboardroomllc",
   "website":"www.zombo.com"
}
```
Set a Supplier attribute to null.

PUT /suppliers/&lt;GUID&gt;?setnull=true

```
{
   "accountNumber":"1",
   "additionalAttributes":[
      {
         "apiName":"custom1411225",
         "fieldType":"DATE",
         "guid":"HZJ2LT22ZGXFYH0J8J6T",
         "name":"Re-Evaluate On",
         "value":"2019-02-01T06:59:59Z"
      },
      {
         "apiName":"custom1411226",
         "fieldType":"FIXED_DROP_DOWN",
         "guid":"I0K3MU330HYGZI1K9K72",
         "name":"At-Risk Supplier?",
         "value":"No"
      },
      {
         "apiName":"custom1411227",
         "fieldType":"DROP_DOWN",
         "guid":"J1L4NV441IZH0J2LAL8A",
         "name":"Product Line",
         "value":"Hades"
      },
      {
         "apiName":"custom1411228",
         "fieldType":"MULTI_LINE_TEXT",
         "guid":"K2M5OW552J0I1K3MBM9V",
         "name":"Internal reviews",
         "value":"Failed to meet deadline."
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
      },
      {
         "address":{
            "label":"sales",
            "address1":"1313 Mockingbird Lane",
            "city":"Smalltown",
            "state":"New York",
            "province":"",
            "postalCode":"01234",
            "Country/Region":"United States"
         },
         "primary":false
      }
   ],
   "approvalStatus":"approved",
   "creationDateTime":"2018-04-27T00:18:52Z",
   "creator":{
      "email":"hwalker@everyroadgps.com",
      "fullName":"Heidi Walker"
   },
   "description":"Full service board house",
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
   "supplierId":null,
   "website":"www.zombo.com"
}
```
Request with bad GUID

```
{  
    "status":400,
    "errors":[  
        {  
            "code":3011,
            "message":"The guid \"XFWQ0GZGZDJ015J12\" is not valid."
        }
    ]
}
```
