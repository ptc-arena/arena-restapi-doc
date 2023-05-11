# POST Change Create


/changes

Creates a new  object. You can create changes with three different types of effectivity:

* Permanent on Approval: The Change becomes effective immediately upon the last necessary vote being entered.

* Permanent on Date: The Change enters the Approved state upon the last necessary vote being entered, but does not become effective until the specified date. Requires the attribute plannedEffectivityDateTime.

* Temporary: Changes with temporary effectivity \(often called Deviations\) become effective immediately upon the last necessary vote being entered, and expire on a specified date. Requires the attribute expirationDate.

In all cases, numberSequencePrefix is required. If a default numberSequencePrefix is associated with the specified change category, not specifying a  numberSequencePrefix will result in automatically selecting the default.  

Below are examples of each type of Change, including all fields that can be created for each effectivity type.

See the 

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content\-type<br> | application/json<br> |   |

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

## Sample Requests and Responses
Create change with permanent\-on\-approval effectivity



POST /changes



```
{
   "category":{
      "guid":"7P9SBO90NQ9J2L0778WO"
   },
   "numberSequencePrefix":{
      "value":"ECO-"
   },
   "title":"EveryRoad Model 300 Case Melting",
   "description":"The Model 300 overheats when the unit is left on in an excessively hot environment. The typical environment would be a vehicle with closed doors on a hot day. In these cases, the unit fails due to chip failure and in rare cases, can cause fire. The resolution to this issue includes increasing the diameter of the cooling holes on the back of the unit, and the addition of a thermal overload circuit to shutdown the EveryRoad before ignition can occur.",
   "routings":[
      {
         "guid":"HZJ2LYJAX0HK3M5O4QR4"
      }
   ],
   "approvalDeadlineDateTime":"2018-09-15T00:00:00Z",
   "enforceApprovalDeadline":true,
   "effectivityType":"PERMANENT_ON_APPROVAL",
   "additionalAttributes":[
      {
         "guid":"6O8RAN8ZMP7UDWDIQH5T",
         "value":"Medium-High"
      },
      {
         "guid":"9QU24KGNKOUGD1Z0RM3X",
         "value":2
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
         "value":"Medium-High"
      },
      {
         "apiName":"custom8397153",
         "fieldType":"NUMBER",
         "guid":"9QU24KGNKOUGD1Z0RM3X",
         "name":"Priority (1-5)",
         "value":2
      }
   ],
   "approvalDeadlineDateTime":"2018-09-15T07:59:59Z",
   "category":{
      "guid":"7P9SBO90NQ9J2L0778WO",
      "name":"Engineering Change Order",
      "path":"Change\\Change Order\\Engineering Change Order"
   },
   "creationDateTime":"2018-02-21T21:38:26Z",
   "creator":{
      "email":"hwalker@everyroadgps.com",
      "fullName":"Heidi Walker",
      "guid":"WEYH0DYPCFWFYH0JSIPD"
   },
   "description":"The Model 300 overheats when the unit is left on in an excessively hot environment. The typical environment would be a vehicle with closed doors on a hot day. In these cases, the unit fails due to chip failure and in rare cases, can cause fire. The resolution to this issue includes increasing the diameter of the cooling holes on the back of the unit, and the addition of a thermal overload circuit to shutdown the EveryRoad before ignition can occur.",
   "effectiveDateTime":null,
   "effectivityType":"PERMANENT_ON_APPROVAL",
   "enforceApprovalDeadline":true,
   "guid":"L3N6P2NE14NQ9R77C5PD",
   "implementationStatus":"NOT_STARTED",
   "lifecycleDateTime":"2018-02-21T21:38:26Z",
   "lifecycleStatus":{
      "type":"OPEN_AND_UNLOCKED"
   },
   "number":"ECO-000026",
   "routings":[
      {
         "guid":"HZJ2LYJAX0HK3M5O4QR4",
         "name":"Production Phase Changes"
      }
   ],
   "submissionDateTime":null,
   "title":"EveryRoad Model 300 Case Melting"
}
```
Change with permanent\-on\-date effectivity



POST /changes



```
{
   "category":{
      "guid":"7P9SBO90NQ9J2L0778WO"
   },
   "numberSequencePrefix":{
      "value":"ECO-"
   },
   "title":"New Fabrication for Everyroad Rear Panel",
   "description":"This change phases in the new fab for the rear panel on the 300 and 500 models. The effectivity date for this change will be April 1st, 2018 regardless of approval date.",
   "routings":[
      {
         "guid":"I0K3MZKBY1IL4N6P5RSG"
      },
      {
         "guid":"2K4N6J4VIL25O7Q9PBCD"
      }
   ],
   "approvalDeadlineDateTime":"2018-03-24T06:59:59Z",
   "enforceApprovalDeadline":true,
   "effectivityType":"PERMANENT_ON_DATE",
   "effectivityPlannedDateTime":"2018-04-01T07:00:00Z",
   "additionalAttributes":[
      {
         "guid":"6O8RAN8ZMP7UDWDIQH5T",
         "value":"Medium-High"
      },
      {
         "guid":"9QU24KGNKOUGD1Z0RM3X",
         "value":"2"
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
         "value":"Medium-High"
      },
      {
         "apiName":"custom8397153",
         "fieldType":"NUMBER",
         "guid":"9QU24KGNKOUGD1Z0RM3X",
         "name":"Priority (1-5)",
         "value":2
      }
   ],
   "approvalDeadlineDateTime":"2018-03-24T06:59:59Z",
   "category":{
      "guid":"7P9SBO90NQ9J2L0778WO",
      "name":"Engineering Change Order",
      "path":"Change\\Change Order\\Engineering Change Order"
   },
   "creationDateTime":"2018-02-21T21:43:30Z",
   "creator":{
      "email":"hwalker@everyroadgps.com",
      "fullName":"Heidi Walker",
      "guid":"WEYH0DYPCFWFYH0JSIPD"
   },
   "description":"This change phases in the new fab for the rear panel on the 300 and 500 models. The effectivity date for this change will be April 1st, 2018 regardless of approval date.",
   "effectiveDateTime":null,
   "effectivityPlannedDateTime":"2018-09-30T07:59:59Z",
   "effectivityType":"PERMANENT_ON_DATE",
   "enforceApprovalDeadline":true,
   "guid":"M4O7Q3OF25ORAS88D6Q9",
   "implementationStatus":"NOT_STARTED",
   "lifecycleDateTime":"2018-02-21T21:43:30Z",
   "lifecycleStatus":{
      "type":"OPEN_AND_UNLOCKED"
   },
   "number":"ECO-000027",
   "routings":[
      {
          "guid": "I0K3MZKBY1IL4N6P5RSG",
          "name": "Component Librarian"
      },
      {
          "guid": "2K4N6J4VIL25O7Q9PBCD",
          "name": "CTO Review"
      }
   ],
   "submissionDateTime":null,
   "title":"New Fabrication for Everyroad Rear Panel"
}
```
Change with temporary effectivity



POST /changes



```
{
   "category":{
      "guid":"4M6P8L6XKN6GZIX445T6"
   },
   "numberSequencePrefix":{
      "value":"DEV-"
   },
   "title":"Temporarily use gray enclosure while black enclosure is unavailable.",
   "description":"Supplier unable to deliver gray enclosure for 3 weeks. Substitute with black until delivery resumes.",
   "routings":[
      {
         "guid":"I0K3MZKBY1IL4N6P5RSG"
      }
   ],
   "effectivityType":"TEMPORARY",
   "expirationDateTime":"2018-10-15T07:59:59Z",
   "additionalAttributes":[
      {
         "guid":"TBVEXAVM9CUH0J05D4RE",
         "value":"< $5000"
      },
      {
         "guid":"6O8RAN8ZMP7UDWDIQH5T",
         "value":"High-Medium"
      },
      {
         "guid":"9QU24KGNKOUGD1Z0RM3X",
         "value":"2"
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
         "value":"Medium-High"
      },
      {
         "apiName":"custom8397153",
         "fieldType":"NUMBER",
         "guid":"9QU24KGNKOUGD1Z0RM3X",
         "name":"Priority (1-5)",
         "value":2
      },
      {
         "apiName":"custom8397153",
         "fieldType":"PREDEFINED_DROP_DOWN",
         "guid":"9QU24KGNKOUGD1Z0RM3X",
         "name":"Cost Impact",
         "value":"< $5000"
      }
   ],
   "category":{
      "guid":"4M6P8L6XKN6GZIX445T6",
      "name":"Deviation",
      "path":"Change\\Deviation"
   },
   "creationDateTime":"2018-02-22T00:33:03Z",
   "creator":{
      "email":"hwalker@everyroadgps.com",
      "fullName":"Heidi Walker",
      "guid":"WEYH0DYPCFWFYH0JSIPD"
   },
   "description":"Supplier unable to deliver gray enclosure for 3 weeks. Substitute with black until delivery resumes.",
   "effectiveDateTime":null,
   "effectivityType":"TEMPORARY",
   "enforceApprovalDeadline":false,
   "expirationDateTime":"2018-10-15T07:59:59Z",
   "guid":"UCWFYBWNADWZI0GGLEYM",
   "implementationStatus":"NOT_STARTED",
   "lifecycleDateTime":"2018-02-22T00:33:03Z",
   "lifecycleStatus":{
      "type":"OPEN_AND_UNLOCKED"
   },
   "number":"DEV-000002",
   "routings":[
      {
         "guid":"I0K3MZKBY1IL4N6P5RSG",
         "name":"Component Librarian"
      }
   ],
   "submissionDateTime":null,
   "title":"Temporarily use gray enclosure while black enclosure is unavailable."
}
```
value supplied for effectivityType does not match  default value enforced for the selected category

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
value supplied for numberingSequence does not match  default value enforced for the selected category

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
Request with invalid GUID

```
{  
    "status":400,
    "errors":[  
        {  
            "code":3045,
            "message":"The GUID 07SFVKE79SLLW285LF8S is invalid."
        }
    ]
}
```
