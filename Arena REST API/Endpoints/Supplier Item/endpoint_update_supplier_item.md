# PUT Supplier Item Update
/supplieritems/&lt;GUID&gt;

Updates the metadata of a Supplier Item with a given GUID. To update values for additional attributes, first retrieve the GUID of each attribute using the GET Supplier Item endpoint.  Updated values must be valid for the attribute.

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content-type<br> | application/json<br> |   |

## Set Null

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| setnull<br> |   | Append the URL with setnull=true to set name, description, or type to null. Attributes must be included within the request body and set to null. Insert setnull after the query string, represented by a ?, after the GUID.<br> |

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

| Code<br> | Description<br> |
|  --- |  --- | 
| 200<br> | Success<br> |
| 400<br> | Failure<br> |

## Response Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| Content-Length<br> | number<br> | number of characters in response<br> |
| Content-Type<br> | application/json<br> | content type of response<br> |
| Date<br> | date<br> | today's date and time<br> |
| Server<br> | ArenaSolutions<br> |   |
| X-Arena-Next-Request-Limit-Reset<br> | date<br> | the scheduled time for resetting of the count<br> |
| X-Arena-Requests-Remaining<br> | number<br> | how many calls left<br> |

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
