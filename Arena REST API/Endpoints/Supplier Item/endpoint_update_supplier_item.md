# PUT Supplier Item Update


/supplieritems/&lt;GUID&gt;

Updates the metadata of a  with a given GUID. To update values for additional attributes, first retrieve the GUID of each attribute using the GET Supplier Item endpoint.  Updated values must be valid for the attribute.

## Request Header

| Name | Value | Description |
|  --- |  --- |  --- | 
| arena_session_id |   | unique ID for session obtained from login |
| content\-type | application/json |   |

## Set Null

| Name | Value | Description |
|  --- |  --- |  --- | 
| setnull |   | Append the URL with setnull=true to set name, description, or type to null. Attributes must be included within the request body and set to null. Insert setnull after the query string, represented by a ?, after the GUID. |

## Sample Request Body
PUT /supplieritems/&lt;GUID&gt;

```
{
   "additionalAttributes":[
      {
         "guid":"ZH1K3BKKHYFXGZI118BV",
         "value":"Yes"
      },
      {
         "guid":"2K4N6ENNK1I0J2L44BET",
         "value":"John Parker"
      },
      {
         "guid":"0I2L4CLLIZGYH0J229CD",
         "value":"Updated note"
      },
      {
         "guid":"YG0J2AJJGXEWFYH007AO",
         "value":"2020-01-01T06:59:59Z"
      },
      {
         "guid":"1J3M5DMMJ0HZI1K33ADK",
         "value":"10"
      }
   ],
   "description":"Rear board half moon",
   "name":"Rear board half moon",
   "number":"BHM-27B6",
   "offTheShelf":true,
   "type":"PART",
   "uom":"each"
}
```
PUT /supplieritems/&lt;GUID&gt;?setnull=true

```
{ 
   "description":null    
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
Update a given supplier item



/supplieritems/&lt;GUID&gt;

```
{
   "additionalAttributes":[
      {
         "apiName":"custom902625",
         "fieldType":"DROP_DOWN",
         "guid":"2K4N6ENNK1I0J2L44BET",
         "name":"First Article Tester",
         "value":"John Parker"
      },
      {
         "apiName":"custom902622",
         "fieldType":"FIXED_DROP_DOWN",
         "guid":"ZH1K3BKKHYFXGZI118BV",
         "name":"Compliance Risk?",
         "value":"Yes"
      },
      {
         "apiName":"custom902623",
         "fieldType":"MULTI_LINE_TEXT",
         "guid":"0I2L4CLLIZGYH0J229CD",
         "name":"Notes",
         "value":"Updated note"
      },
      {
         "apiName":"custom902624",
         "fieldType":"SINGLE_LINE_TEXT",
         "guid":"1J3M5DMMJ0HZI1K33ADK",
         "name":"Stock EOQ",
         "value":"10"
      },
      {
         "apiName":"custom902621",
         "fieldType":"DATE",
         "guid":"YG0J2AJJGXEWFYH007AO",
         "name":"Re-Evaluate On",
         "value":"2020-01-01T07:59:59Z"
      }
   ],
   "creationDateTime":"2018-04-27T22:55:36Z",
   "creator":{
      "email":"hwalker@everyroadgps.com",
      "fullName":"Heidi Walker"
   },
   "description":"Rear board half moon",
   "guid":"I0K3MU330H05O7QRXRV8",
   "name":"Rear board half moon",
   "number":"BHM-27B6",
   "offTheShelf":true,
   "supplier":{
      "guid":"UCWFY6FFCTCI1K3B82OC"
   },
   "type":"PART",
   "uom":"each"
}
```
Set a Supplier Item attribute to null.

PUT /supplieritems/&lt;GUID&gt;?setnull=true

```
{
   "additionalAttributes":[
      {
         "apiName":"custom902625",
         "fieldType":"DROP_DOWN",
         "guid":"2K4N6ENNK1I0J2L44BET",
         "name":"First Article Tester",
         "value":"John Parker"
      },
      {
         "apiName":"custom902622",
         "fieldType":"FIXED_DROP_DOWN",
         "guid":"ZH1K3BKKHYFXGZI118BV",
         "name":"Compliance Risk?",
         "value":"Yes"
      },
      {
         "apiName":"custom902623",
         "fieldType":"MULTI_LINE_TEXT",
         "guid":"0I2L4CLLIZGYH0J229CD",
         "name":"Notes",
         "value":"Updated note"
      },
      {
         "apiName":"custom902624",
         "fieldType":"SINGLE_LINE_TEXT",
         "guid":"1J3M5DMMJ0HZI1K33ADK",
         "name":"Stock EOQ",
         "value":"10"
      },
      {
         "apiName":"custom902621",
         "fieldType":"DATE",
         "guid":"YG0J2AJJGXEWFYH007AO",
         "name":"Re-Evaluate On",
         "value":"2020-01-01T07:59:59Z"
      }
   ],
   "creationDateTime":"2018-04-27T22:55:36Z",
   "creator":{
      "email":"hwalker@everyroadgps.com",
      "fullName":"Heidi Walker"
   },
   "description":null,
   "guid":"I0K3MU330H05O7QRXRV8",
   "name":"Rear board half moon",
   "number":"BHM-27B6",
   "offTheShelf":true,
   "supplier":{
      "guid":"UCWFY6FFCTCI1K3B82OC"
   },
   "type":"PART",
   "uom":"each"
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
