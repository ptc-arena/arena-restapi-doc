# PUT Change Edit


/changes/&lt;GUID&gt;

Updates attribute information for a change with a given GUID. 

For an overview of the Change Lifecyle in Arena, including a summary of Lifecycle Rules, see .

Changes cannot be edited after they are submitted, with the following exceptions:

* Approval Deadline and Expiration Date can be edited on Submitted and Effective Changes by Change Administrator users.

* Implementation Status can be edited in any lifecycle phase.

The fields you can update are dependent on the Change's effectivity type. 


| Permanent on Approval<br> | Permanent on Date<br> | Temporary<br> |
|  --- |  --- |  --- | 
| category; title; description; approvalDeadline; effectivityType\*; enforceApprovalDeadline; implementationStatus; Additional Attribute values<br> | category; title; description; approvalDeadline; effectivityType\*; enforceApprovalDeadline; implementationStatus; Additional Attribute values<br> | category; title; description; approvalDeadline; enforceApprovalDeadline; expirationDateTime; implementationStatus; Additional Attribute values<br> |

\*For Changes with Permanent Effectivity, effectivityType can be edited to the other Permanent value, but cannot be changed to Temporary. For Changes with Temporary Effectivity, effectivityType cannot be edited. 

See the 

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content\-type<br> | application/json<br> |   |

## Set Null

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| setnull<br> |   | Append the URL with setnull=true to set implementationStatus, approvalDeadlineDateTime, title, and description to null. Attributes must be included within the request body and set to null. Insert setnull after the query string, represented by a ?, after the GUID<br> |

## Response Codes

| Code<br> | Description<br> |
|  --- |  --- | 
| 200<br> | Success<br> |
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

## Sample Requests and Responses
Edit a Change with permanent\-on\-approval effectivity

/changes/&lt;GUID&gt;



```
{
   "category":{
      "guid":"7P9SBO90NQ9J2L0778WO"
   },
   "title":"New Injection Molding for Everyroad Rear Panel",
   "description":"Updated design for Rear Panel 432-00003. This panel is used in the 500 model Everyroad GPS.\n\nModifications on Sourcing, and Files views. EDIT--see new dimensions for clearance.",
   "approvalDeadlineDateTime":"2018-09-15T00:00:00Z",
   "effectivityType":"PERMANENT_ON_APPROVAL",
   "enforceApprovalDeadline":true,
   "implementationStatus":"NOT_STARTED",
   "additionalAttributes":[
      {
         "guid":"6O8RAN8ZMP7UDWDIQH5T",
         "value":"High-Medium"
      }
   ]
}
```


```
{
   "additionalAttributes":[
      {
         "apiName":"custom2361807",
         "fieldType":"FIXED_DROP_DOWN",
         "guid":"6O8RAN8ZMP7UDWDIQH5T",
         "name":"Urgency",
         "value":"High-Medium"
      }
   ],
   "approvalDeadlineDateTime":"2018-09-15T00:00:00Z",
   "category":{
      "guid":"7P9SBO90NQ9J2L0778WO",
      "name":"Engineering Change Order",
      "path":"Change\\Change Order\\Engineering Change Order"
   },
   "creationDateTime":"2016-11-18T19:31:15Z",
   "creator":{
      "email":"hwalker@everyroadgps.com",
      "fullName":"Heidi Walker",
      "guid":"WEYH0DYPCFWFYH0JSIPD"
   },
   "description":"Updated design for Rear Panel 432-00003. This panel is used in the 500 model Everyroad GPS.\n\nModifications on Sourcing, and Files views. EDIT--see new dimensions for clearance.",
   "effectiveDateTime":null,
   "effectivityType":"PERMANENT_ON_APPROVAL",
   "enforceApprovalDeadline":true,
   "guid":"Q8SBU7SJ69SVEWCEKLBO",
   "implementationStatus":"NOT_STARTED",
   "lifecycleDateTime":"2016-11-18T19:31:15Z",
   "lifecycleStatus":{
      "type":"OPEN_AND_UNLOCKED"
   },
   "number":"ECO-000020",
   "routings":[
      {
         "guid":"HZJ2LYJAX0HK3M5O4QR4",
         "name":"Production Phase Changes"
      }
   ],
   "submissionDateTime":null,
   "title":"New injection molding for Everyroad Rear Panel"
}
```
Edit a Change with permanent\-on\-date effectivity

/changes/&lt;GUID&gt;



```
{
   "category":{
      "guid":"7P9SBO90NQ9J2L0778WO"
   },
   "title":"New Fabrication for Everyroad Rear Panel",
   "description":"This change phases in the new fab for the rear panel on the 300 and 500 models. The effectivity date for this change will be April 1st, 2018 regardless of approval date.",
   "approvalDeadlineDateTime":"2018-09-15T00:00:00Z",
   "effectivityPlannedDateTime":"2018-04-01T07:00:00Z",
   "effectivityType":"PERMANENT_ON_DATE",
   "enforceApprovalDeadline":true,
   "implementationStatus":"NOT_STARTED",
   "additionalAttributes":[
      {
         "guid":"6O8RAN8ZMP7UDWDIQH5T",
         "value":"High-Medium"
      }
   ]
}
```


```
{
   "additionalAttributes":[
      {
         "apiName":"custom2361807",
         "fieldType":"FIXED_DROP_DOWN",
         "guid":"6O8RAN8ZMP7UDWDIQH5T",
         "name":"Urgency",
         "value":"High-Medium"
      }
   ],
   "approvalDeadlineDateTime": "2018-03-24T06:59:59Z",
   "category": {
       "guid": "7P9SBO90NQ9J2L0778WO",
       "name": "Engineering Change Order",
       "path": "Change\\Change Order\\Engineering Change Order"
   },
   "creationDateTime": "2018-03-07T01:17:44Z",
   "creator": {
       "email": "hwalker@everyroadgps.com",
       "fullName": "Heidi Walker",
       "guid": "WEYH0DYPCFWFYH0JSIPD"
   },
   "description": "This change phases in the new fab for the rear panel on the 300 and 500 models. The effectivity date for this change will be April 1st, 2018 regardless of approval date.",
   "effectiveDateTime": null,
   "effectivityPlannedDateTime": "2018-04-01T07:00:00Z",
   "effectivityType": "PERMANENT_ON_DATE",
   "enforceApprovalDeadline":true,
   "guid": "5N7Q9M7YLO7ATBRRWSLF",
   "implementationStatus": "NOT_STARTED",
   "lifecycleDateTime": "2018-03-07T18:52:06Z",
   "lifecycleStatus": {
      "type": "OPEN_AND_UNLOCKED"
   },
   "number": "ECO-000022",
   "routings": [
      {
         "guid": "I0K3MZKBY1IL4N6P5RSG",
         "name": "Component Librarian"
      },
      {
         "guid": "2K4N6J4VIL25O7Q9PBCD",
         "name": "CTO Review"
      }
   ],
   "submissionDateTime": "2018-03-07T01:21:20Z",
   "submitter": {
      "email": "hwalker@everyroadgps.com",
      "fullName": "Heidi Walker",
      "guid": "WEYH0DYPCFWFYH0JSIPD"
   },
   "title": "New Fabrication for Everyroad Rear Panel",
   "withdrawnDateTime": "2018-03-07T18:52:06Z"
}
```
Edit a Change with temporary effectivity

/changes/&lt;GUID&gt;



```
{
   "category":{
      "guid":"4M6P8L6XKN6GZIX445T6"
   },
   "title":"Use Alternate Chipset with New Logic in 500 Boards",
   "description":"The chipset at U1, U3, U17 can be programmed with the new logic X89c12. Allow use of the alternate chips at these locations until supply is exhausted. EDIT-Add U14.",
   "approvalDeadlineDateTime":"2018-03-10T07:59:59Z",
   "enforceApprovalDeadline":false,
   "expirationDateTime": "2018-03-28T07:00:00Z"
   "implementationStatus":"NOT_STARTED",
   "additionalAttributes":[
      {
         "guid":"6O8RAN8ZMP7UDWDIQH5T",
         "value":"High-Medium"
      }
   ]
}
```


```
{
   "additionalAttributes":[
      {
         "apiName":"custom2361807",
         "fieldType":"FIXED_DROP_DOWN",
         "guid":"6O8RAN8ZMP7UDWDIQH5T",
         "name":"Urgency",
         "value":"High-Medium"
      }
   ],
   "approvalDeadlineDateTime":"2018-03-10T07:59:59Z",
   "category":{
      "guid":"4M6P8L6XKN6GZIX445T6",
      "name":"Deviation",
      "path":"Change\\Deviation"
   },
   "creationDateTime":"2018-03-07T00:53:59Z",
   "creator":{
      "email":"hwalker@everyroadgps.com",
      "fullName":"Heidi Walker",
      "guid":"WEYH0DYPCFWFYH0JSIPD"
   },
   "description":"The chipset at U1, U3, U17 can be programmed with the new logic X89c12. Allow use of the alternate chips at these locations until supply is exhausted. EDIT-Add U14.",
   "effectiveDateTime":null,
   "effectivityType":"TEMPORARY",
   "enforceApprovalDeadline":false,
   "expirationDateTime":"2018-03-28T07:00:00Z",
   "guid":"3L5O7K5WJM58R9PPUQJC",
   "implementationStatus":"NOT_STARTED",
   "lifecycleDateTime":"2018-03-07T00:53:59Z",
   "lifecycleStatus":{
      "type":"OPEN_AND_UNLOCKED"
   },
   "number":"DEV-000002",
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
   "submissionDateTime":null,
   "title":"Use Alternate Chipset with New Logic in 500 Boards"
}
```
Set a change attribute to null.

PUT /changes/&lt;GUID&gt;?setnull=true



```
{
    "implementationStatus": null
}
```


```
{
   "additionalAttributes":[
      {
         "apiName":"custom2361807",
         "fieldType":"FIXED_DROP_DOWN",
         "guid":"6O8RAN8ZMP7UDWDIQH5T",
         "name":"Urgency",
         "value":"High-Medium"
      }
   ],
   "approvalDeadlineDateTime":"2018-03-10T07:59:59Z",
   "category":{
      "guid":"4M6P8L6XKN6GZIX445T6",
      "name":"Deviation",
      "path":"Change\\Deviation"
   },
   "creationDateTime":"2018-03-07T00:53:59Z",
   "creator":{
      "email":"hwalker@everyroadgps.com",
      "fullName":"Heidi Walker",
      "guid":"WEYH0DYPCFWFYH0JSIPD"
   },
   "description":"The chipset at U1, U3, U17 can be programmed with the new logic X89c12. Allow use of the alternate chips at these locations until supply is exhausted. EDIT-Add U14.",
   "effectiveDateTime":null,
   "effectivityType":"TEMPORARY",
   "enforceApprovalDeadline":false,
   "expirationDateTime":"2018-03-28T07:00:00Z",
   "guid":"3L5O7K5WJM58R9PPUQJC",
   "implementationStatus":null,
   "lifecycleDateTime":"2018-03-07T00:53:59Z",
   "lifecycleStatus":{
      "type":"OPEN_AND_UNLOCKED"
   },
   "number":"DEV-000002",
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
   "submissionDateTime":null,
   "title":"Use Alternate Chipset with New Logic in 500 Boards"
}
```
Attempt to move a Change beteween permanent and temporary effectivity

```
{  
    "status":400,
    "errors":[  
        {  
            "code":4019,
            "message":"Effectivity cannot be modified because once created, a Change cannot move between permanent and temporary effectivity."
        }
    ]
}
```
effectivityType has an enforced default value and cannot be edited

```
{  
    "status":400,
    "errors":[  
        {  
            "code":4014,
            "message":"The default value for effectivityType is enforced for Changes assigned to this category, so the supplied value must match the default."
        }
    ]
}
```
numberingSequence has an enforced default value and cannot be edited

```
{  
    "status":400,
    "errors":[  
        {  
            "code":4015,
            "message":"The default value for numberingSequence is enforced for Changes assigned to this category, so the supplied value must match the default."
        }
    ]
}
```
Category cannot be selected because it has an enforced default value for effectivityType which does not match the current value

```
{  
    "status":400,
    "errors":[  
        {  
            "code":4017,
            "message":"This Change cannot be assigned to the specified category because that category’s enforced default effectivity is not allowed."
        }
    ]
}
```
Category cannot be selected because it has an enforced default value for numberingSequence which does not match the current value

```
{  
    "status":400,
    "errors":[  
        {  
            "code":4018,
            "message":"This Change cannot be assigned to the specified category because once created, a Change cannot move to a different number sequence."
        }
    ]
}
```
Change cannot be updated in the current lifecycle stage

```
{  
    "status":400,
    "errors":[  
        {  
            "code":4020,
            "message":"The change cannot be updated at this lifecycle stage."
        }
    ]
}
```
Request with invalid GUID

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
