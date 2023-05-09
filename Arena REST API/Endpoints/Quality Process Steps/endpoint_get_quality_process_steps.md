# GET Quality Process Steps


/qualityprocesses/&lt;GUID&gt;/steps

Returns a collection of   objects for a  Quality Process with a given GUID.

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
Get steps for a given quality process



/qualityprocesses/&lt;GUID&gt;/steps

```
{
   "count":6,
   "results":[
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
         ],
         "attributes":[
            {
               "apiName":"custom890",
               "fieldType":"MULTI_LINE_TEXT",
               "guid":"8QATCKTTQ7O6P8RATC7Q",
               "name":"Problem Description",
               "value":"Bad sensor in X27 was noted at 80% failure and went full failure, causing a short that fried the board."
            }
         ],
         "completeDateTime":"2018-09-04T01:32:03Z",
         "completeUser":{
            "fullName":"John Parker"
         },
         "dueDateTime":"2018-09-04T06:59:59Z",
         "guid":"BTDWFNWWTATP8RATBC4E",
         "name":"Problem Description",
         "order":1,
         "status":"COMPLETE",
         "type":"REGULAR"
      },
      {
         "approvals":null,
         "assignee":null,
         "assignee": {
             "userGroups": [
                 {
                     "guid": "BTDWFSD4RU0N6P8RA955",
                     "name": "Quality Assurance",
                     "users": [
                         {
                             "fullName":"James Deckard",
                             "guid":"6O8RAIRRO5M5O7Q9SOLD"
                         },
                         {
                             "fullName":"Caroline Goff ", 
                             "guid":"5N7Q9M7YL0507Q9SY0E7"  
                         },
                         {
                             "fullName":"Peter Yeh",
                             "guid":"0I2L4H2TGJ0J2L4NWMTA"
                         }
                     ]
 
                 }
         ],
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
      },
      {
         "approvals":null,
         "assignee":{
            "deprecated": true,
            "fullName":"Rachael Borger",
            "guid":"9RBUDLUUR8P8RATCVROR",
            "note": "The assignee response object is deprecated. Please use assignees."
         },
         "assignees": {
            "users": [
               {
                  "fullName": "Rachael Borger",
                  "guid": "9RBUDLUUR8P8RATCVROR"
               }
            ],
         }
         "attributes":[
            {
               "apiName":"custom897",
               "fieldType":"MULTI_LINE_TEXT",
               "guid":"FXH0JR00XEVDWFYH0JE4",
               "name":"Possible Causes",
               "value":"There is not enough clearance for adequate venting on the board."
            },
            {
               "apiName":"custom898",
               "fieldType":"MULTI_LINE_TEXT",
               "guid":"GYI1KS11YFWEXGZI1KF5",
               "name":"5 Whys",
               "value":"Why 1: How can we fix the clearance problem?\nResponse: New molding for front cover\nWhy 2: Why did testing not catch this?\nResponse: Our tests were performed with the same cover, but it is possible a burring flaw limited the clearance\nWhy 3: Why did we not catch burring flaws on this shipment?\nResponse: Unknown\nWhy 4: Why did our tooling process allow burring?\nResponse: We were nearing the next calibration. Possibly a tooling machine failed.\nWhy 5: Why are we not calibrating more often?\nResponse: Good question. We should review this interval."
            }
         ],
         "completeDateTime":null,
         "completeUser":null,
         "dueDateTime":"2018-09-06T06:59:59Z",
         "guid":"DVFYHPYYVCVRATCVDE6Z",
         "name":"Root Cause Analysis",
         "order":3,
         "status":"OPEN",
         "type":"REGULAR"
      },
      {
         "allowOwnerToAddApprovers":true,
         "approvals":null,
         "assignee":null,
         "completeDateTime":null,
         "completeUser":null,
         "dueDateTime":null,
         "guid":"EWGZIQZZWDWSBUDWEF7A",
         "name":"Root Cause Confirmation",
         "order":4,
         "status":"OPEN",
         "type":"SIGNOFF"
      },
      ...
   ]
}
```
Returns an error if the GUID is not valid

```
{
  "status": 400,
  "errors": [
    {
      "code": 3011,
      "message": "The guid \"XFWQ0GZGZDJ015J12\" is not valid."
    }
  ]
}
```
