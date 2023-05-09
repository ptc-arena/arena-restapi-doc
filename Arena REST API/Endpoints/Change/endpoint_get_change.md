# GET Change


/changes/&lt;GUID&gt;

Returns a  object with a given GUID. The attributes returned in the response differ according to the effectivityType. For example, a Change with a future effectivity \(effectivityType=PERMANENT_ON_DATE\) includes the attribute effectivityPlannedDateTime.

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
| Content\-Type | application/json | content type of response |
| Date | date | today's date and time |
| Server | ArenaSolutions |   |
| X\-Arena\-Next\-Request\-Limit\-Reset  | date | the scheduled time for resetting of the count |
| X\-Arena\-Requests\-Remaining  | number | how many calls left |

## Sample Response Body
Get a change with permanent\-on\-approval effectivity

 

GET /changes/&lt;GUID&gt;

```
{
   "additionalAttributes":[
      {
         "apiName":"custom2269737",
         "fieldType":"FIXED_DROP_DOWN",
         "guid":"FXH0JR00XEVDWFYGNJQZ",
         "multiSelect":false,
         "name":"Urgency",
         "value":"High"
      },
      {
         "apiName":"custom2361807",
         "fieldType":"FIXED_DROP_DOWN",
         "guid":"ZH1K3BKKHYFXGZI0528P",
         "multiSelect":false,
         "name":"Cost over $500?",
         "value":"Yes"
      },
      {
         "apiName":"custom8397153",
         "fieldType":"NUMBER",
         "guid":"9QU24KGNKOUGD1Z0RM3X",
         "name":"Priority (1-5)",
         "value":2
      }
   ],
   "approvalDeadlineDateTime":"2018-06-01T06:59:59Z",
   "category":{
      "guid":"L3N6PX663K3DWFYF3F6C",
      "name":"Engineering Change Order",
      "path":"Change\\Change Order\\Engineering Change Order"
   },
   "creationDateTime":"2014-07-16T23:43:07Z",
   "creator":{
      "email":"hwalker@everyroadgps.com",
      "fullName":"Heidi Walker",
      "guid":"4M6P8GPPM3K3M5O7QMJ9"
   },
   "description":"3 components in the Everyroad board are going to go end of life in the next 6 months. I have sourced replacements from SiliconExpert.",
   "effectiveDateTime":null,
   "effectivityType":"PERMANENT_ON_APPROVAL",
   "enforceApprovalDeadline":false,
   "guid":"K2M5OW552J25O6PAIDQZ",
   "implementationStatus":"NOT_STARTED",
   "lifecycleDateTime":"2018-05-23T22:35:41Z",
   "lifecycleStatus":{
      "type":"OPEN_AND_UNLOCKED"
   },
   "number":"ECO-000011",
   "routingAdmins": [
       {
         "email": "hwalker@everyroadgps.com",
         "fullName": "Heidi Walker",
         "guid": "WEYH0DYPCFWFYH0JSIPD"
       }
     ],
   "routings":[
      {
         "guid":"J1L4NV441IZ2L4N6P3EZ",
         "name":"Approval Routing"
      }
   ],
   "submissionDateTime":"2014-07-16T23:43:54Z",
   "submitter":{
      "email":"hwalker@everyroadgps.com",
      "fullName":"Heidi Walker",
      "guid":"4M6P8GPPM3K3M5O7QMJ9"
   },
   "title":"Replace at-risk components in EveryRoad PCBA",
   "withdrawnDateTime":"2018-05-23T22:35:41Z"
}
```
Get a change with permanent\-on\-date effectvity



GET /changes/&lt;GUID&gt;

```
{
   "additionalAttributes":[
      {
         "apiName":"custom2269737",
         "fieldType":"FIXED_DROP_DOWN",
         "guid":"FXH0JR00XEVDWFYGNJQZ",
         "multiSelect":false,
         "name":"Urgency",
         "value":"High"
      },
      {
         "apiName":"custom2361807",
         "fieldType":"FIXED_DROP_DOWN",
         "guid":"ZH1K3BKKHYFXGZI0528P",
         "multiSelect":false,
         "name":"Cost over $500?",
         "value":"No"
      },
      {
         "apiName":"custom8397153",
         "fieldType":"NUMBER",
         "guid":"9QU24KGNKOUGD1Z0RM3X",
         "name":"Priority (1-5)",
         "value":1
      }
   ],
   "approvalDeadlineDateTime":"2018-06-01T06:59:59Z",
   "category":{
      "guid":"L3N6PX663K3DWFYF3F6C",
      "name":"Engineering Change Order",
      "path":"Change\\Change Order\\Engineering Change Order"
   },
   "creationDateTime":"2018-05-01T11:40:11Z",
   "creator":{
      "email":"hwalker@everyroadgps.com",
      "fullName":"Heidi Walker",
      "guid":"4M6P8GPPM3K3M5O7QMJ9"
   },
   "description":"This change phases in the new fab for the rear panel on the 300 and 500 models. The effectivity date for this change will be July 1st, 2018 regardless of approval date.",
   "effectiveDateTime":null,
   "effectivityPlannedDateTime":"2018-07-01T07:00:00Z",
   "effectivityType":"PERMANENT_ON_DATE",
   "enforceApprovalDeadline":false,
   "guid":"5N7Q9M7YLO7ATBRRWSLF",
   "implementationStatus":"NOT_STARTED",
   "lifecycleDateTime":"2018-05-23T22:35:41Z",
   "lifecycleStatus":{
      "type":"SUBMITTED_FOR_APPROVAL"
   },
   "number":"ECO-000022",
   "routingAdmins": [
       {
         "email": "hwalker@everyroadgps.com",
         "fullName": "Heidi Walker",
         "guid": "WEYH0DYPCFWFYH0JSIPD"
       }
     ],
   "routings":[
      {
         "guid":"I0K3MZKBY1IL4N6P5RSG",
         "name":"Component Librarian"
      },
      {
         "guid":"2K4N6J4VIL25O7Q9PBCD",
         "name":"CTO Review"
      }
   ],
   "submissionDateTime":"2014-07-16T23:43:54Z",
   "submitter":{
      "email":"hwalker@everyroadgps.com",
      "fullName":"Heidi Walker",
      "guid":"4M6P8GPPM3K3M5O7QMJ9"
   },
   "title":"New Fabrication for Everyroad Rear Panel,
}
```
Get a change with temporary effectivity



GET /changes/&lt;GUID&gt;

```
{
   "additionalAttributes":[
      {
         "apiName":"custom2361807",
         "fieldType":"FIXED_DROP_DOWN",
         "guid":"ZH1K3BKKHYFXGZI0528P",
         "multiSelect":false,
         "name":"Cost over $500?",
         "value":"No"
      },
      {
         "apiName":"custom8397153",
         "fieldType":"NUMBER",
         "guid":"9QU24KGNKOUGD1Z0RM3X",
         "name":"Priority (1-5)",
         "value":1
      }
   ],
   "approvalDeadlineDateTime":"2018-06-01T06:59:59Z",
   "category":{
      "guid":"O6Q9S0996N6GZI1I6I94",
      "name":"Deviation",
      "path":"Change\\Deviation"
   },
   "creationDateTime":"2018-05-23T23:08:20Z",
   "creator":{
      "email":"hwalker@everyroadgps.com",
      "fullName":"Heidi Walker",
      "guid":"4M6P8GPPM3K3M5O7QMJ9"
   },
   "description":"The Bezel used for the 300 model is compatible with the 500 model. Acceptable deviation until August 2018.",
   "effectiveDateTime":null,
   "effectivityType":"TEMPORARY",
   "enforceApprovalDeadline":false,
   "expirationDateTime":"2018-08-01T07:00:00Z",
   "guid":"SAUDW4DDARADWEXINFET",
   "implementationStatus":"NOT_STARTED",
   "lifecycleDateTime":"2018-05-23T23:09:44Z",
   "lifecycleStatus":{
      "type":"SUBMITTED_FOR_APPROVAL"
   },
   "number":"DEV-000001",
   "routingAdmins": [
       {
         "email": "hwalker@everyroadgps.com",
         "fullName": "Heidi Walker",
         "guid": "WEYH0DYPCFWFYH0JSIPD"
       }
     ],
   "routings":[
      {
         "guid":"J1L4NV441IZ2L4N6P3EZ",
         "name":"Approval Routing"
      }
   ],
   "submissionDateTime":"2018-05-23T23:09:44Z",
   "submitter":{
      "email":"hwalker@everyroadgps.com",
      "fullName":"Heidi Walker",
      "guid":"4M6P8GPPM3K3M5O7QMJ9"
   },
   "title":"Use Existing Stock for EveryRoad Bezel"
}
```
Request with bad GUID

```
{  
    "status":400,
    "errors":[  
        {  
            "code":3011,
            "message":"The guid \"ASCVERC3QTCFYGPWW1WCS\" is not valid"
        }
    ]
}
```
