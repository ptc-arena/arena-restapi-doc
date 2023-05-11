# POST Supplier Item Create


/supplieritems

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
   "additionalAttributes":[
      {
         "guid":"ZH1K3BKKHYFXGZI118BV",
         "value":"No"
      },
      {
         "guid":"2K4N6ENNK1I0J2L44BET",
         "value":"Testing Lead"
      },
      {
         "guid":"0I2L4CLLIZGYH0J229CD",
         "value":"Always check for stock"
      },
      {
         "guid":"YG0J2AJJGXEWFYH007AO",
         "value":"2019-01-01T06:59:59Z"
      },
      {
         "guid":"1J3M5DMMJ0HZI1K33ADK",
         "value":"100"
      }
   ],
   "description":"Rear board crescent moon",
   "name":"Rear board crescent moon",
   "number":"BHM-27B6",
   "offTheShelf":true,
   "supplier":{
      "guid":"UCWFY6FFCTCI1K3B82OC"
   },
   "uom":"each"
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
Create a new supplier item



/supplieritems

```
{
    "additionalAttributes": [
        {
            "apiName": "custom902625",
            "fieldType": "DROP_DOWN",
            "guid": "2K4N6ENNK1I0J2L44BET",
            "name": "First Article Tester",
            "value": "Testing Lead"
        },
        {
            "apiName": "custom902622",
            "fieldType": "FIXED_DROP_DOWN",
            "guid": "ZH1K3BKKHYFXGZI118BV",
            "name": "Compliance Risk?",
            "value": "No"
        },
        {
            "apiName": "custom902623",
            "fieldType": "MULTI_LINE_TEXT",
            "guid": "0I2L4CLLIZGYH0J229CD",
            "name": "Notes",
            "value": "Always check for stock"
        },
        {
            "apiName": "custom902624",
            "fieldType": "SINGLE_LINE_TEXT",
            "guid": "1J3M5DMMJ0HZI1K33ADK",
            "name": "Stock EOQ",
            "value": "100"
        },
        {
            "apiName": "custom902621",
            "fieldType": "DATE",
            "guid": "YG0J2AJJGXEWFYH007AO",
            "name": "Re-Evaluate On",
            "value": "2019-01-01T07:59:59Z"
        }
    ],
    "creationDateTime": "2018-04-27T22:55:36Z",
    "creator": {
        "email": "hwalker@everyroadgps.com",
        "fullName": "Heidi Walker"
    },
    "description": "Rear board crescent moon",
    "guid": "I0K3MU330H05O7QRXRV8",
    "name": "Rear board crescent moon",
    "number": "BHM-27B6",
    "offTheShelf":true,
    "supplier": {
        "guid": "UCWFY6FFCTCI1K3B82OC"
    },
    "type": "PART",
    "uom": "each"
}
```
Returns an error if:

* the format of the request is incorrect:

```
{  
   "status":400,
   "errors":[  
      {  
         "code":400,
         "message":"The format of the request is not valid. Please check the syntax."
      }
   ]
}
```
* a general error occurs:

```
{  
   "status":400,
   "errors":[  
      {  
         "code":4000,
         "message":"Sorry, a system error occurred, please try again."
      }
   ]
}
```
