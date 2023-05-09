# GET Supplier Item Specs


/supplieritems/&lt;GUID&gt;

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
