# GET Quality Process Step
/qualityprocesses/&lt;GUID&gt;/steps/&lt;GUID&gt;

Returns a Quality Process Step object with a given GUID for a  Quality Process with a given GUID.

## Request Header

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| arena_session_id  |   | unique ID for session obtained from login  |
| content-type  | application/json  |   |

## Parameters

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| includeEmptyAdditionalAttributes  | true or false  | If this is true, the response returns empty additional attributes. The default is false.  |

## Response Codes

| Code  | Description  |
|  --- |  --- | 
| 200  | Success  |
| 400  | Failure  |

## Response Header

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| Content-Length  | number  | number of characters in response  |
| Content-Type  | application/json  | content type of response  |
| Date  | date  | today's date and time  |
| Server  | ArenaSolutions  |   |
| X-Arena-Next-Request-Limit-Reset   | date  | the scheduled time for resetting of the count  |
| X-Arena-Requests-Remaining   | number  | how many calls left  |

## Sample Response Body
Get a single step for a given quality process

/qualityprocesses/&lt;GUID&gt;/steps/&lt;GUID&gt;

```
{
   "approvals":null,
   "assignee":{
       "deprecated": true,
       "fullName":"John Parker",
       "guid":"7P9SBJSSP6N6P8RATPM6",
       "note": "The assignee response object is deprecated. Please use assignees."
   },
   "assignees": {
       "users": [
           {
               "fullName": "John Parker",
               "guid": "7P9SBJSSP6N6P8RATPM6"
           }
       ]
   },    
   "attributes":[
      {
         "apiName":"custom891",
         "fieldType":"SINGLE_LINE_TEXT",
         "guid":"9RBUDLUUR8P7Q9SBUD83",
         "name":"Serial Number(s) of Nonconforming Parts",
         "value":"04444444781"
      },
      {
         "apiName":"custom892",
         "fieldType":"FIXED_DROP_DOWN",
         "guid":"ASCVEMVVS9Q8RATCVE9P",
         "name":"Inventory Impact?",
         "value":"Yes"
      },
      {
         "apiName":"custom893",
         "fieldType":"MULTI_LINE_TEXT",
         "guid":"BTDWFNWWTAR9SBUDWFAK",
         "name":"Inventory Impact description",
         "value":"Review all X27 boards"
      },
      {
         "apiName":"custom894",
         "fieldType":"MULTI_LINE_TEXT",
         "guid":"CUEXGOXXUBSATCVEXGBH",
         "name":"Supplier Containment actions required",
         "value":"Stop-ship from Plasmus."
      },
      {
         "apiName":"custom895",
         "fieldType":"MULTI_LINE_TEXT",
         "guid":"DVFYHPYYVCTBUDWFYHCF",
         "name":"Internal Containment actions required",
         "value":"Hold on production"
      },
      {
         "apiName":"custom896",
         "fieldType":"MULTI_LINE_TEXT",
         "guid":"EWGZIQZZWDUCVEXGZIDO",
         "name":"Customer Containment actions required",
         "value":"Notify all X27 100 batch buyers to discontinue usage."
      }
   ],
   "completeDateTime":"2018-09-04T01:34:38Z",
   "completeUser":{
      "fullName":"James Deckard"
   },
   "dueDateTime":"2018-09-04T06:59:59Z",
   "guid":"CUEXGOXXUBUQ9SBUCD5K",
   "name":"Immediate Containment",
   "order":2,
   "status":"COMPLETE",
   "type":"REGULAR"
}
```
Produces an error if the step GUID is not valid.

```
{
  "status": 400,
  "errors": [
    {
      "code": 3011,
      "message": "The guid \"CUB5FVEN6P8RAQI\" is not valid."
    }
  ]
}
```
