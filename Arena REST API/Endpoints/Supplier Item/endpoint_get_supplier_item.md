# GET Supplier Item Specs
/supplieritems/&lt;GUID&gt;

Returns a Supplier Item object with a given GUID.

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content-type<br> | application/json<br> |   |

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
Get a supplier item with a given GUID

/supplieritems/&lt;GUID&gt;

```
{
   "additionalAttributes":[
      {
         "apiName":"custom903623",
         "fieldType":"DROP_DOWN",
         "guid":"L3N6PX663K1J2L4NNT4Z",
         "name":"First Article Tester",
         "value":"John Parker"
      },
      {
         "apiName":"custom903621",
         "fieldType":"MULTI_LINE_TEXT",
         "guid":"J1L4NV441IZH0J2LLR20",
         "name":"Notes",
         "value":"FXH0JR00XEX3M5OW55VA"
      },
      {
         "apiName":"custom903622",
         "fieldType":"NUMBER",
         "guid":"K2M5OW552J0I1K3MMS3M",
         "name":"Stock EOQ",
         "value":100
      }
   ],
   "creationDateTime":"2011-02-11T17:13:11Z",
   "creator":{
      "email":"hwalker@everyroadgps.com",
      "fullName":"Heidi Walker"
   },
   "description":null,
   "guid":"I0K3MU330H05O7QXOXQY",
   "name":"Logic Output Photo Detector",
   "number":"SFH5110-40",
   "offTheShelf":true,
   "supplier":{
      "guid":"FXH0JR00XEX3M5OW55VA"
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
