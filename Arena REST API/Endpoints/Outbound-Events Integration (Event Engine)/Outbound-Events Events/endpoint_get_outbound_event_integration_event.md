# GET Outbound-Event Integration Event
/outboundevents/&lt;GUID&gt;/events/&lt;GUID&gt;

Returns a specific event for an outbound-event integration with a specific GUID.

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
Get a specific outbound-event integration event.

GET /outboundevents/&lt;GUID&gt;/events/&lt;GUID&gt;

```
{
    "creationDateTime": "2021-08-26T22:28:58Z",
    "creator": {
        "email": "hwalker@everyroadgps.com",
        "fullName": "Heidi Walker",
        "guid": "WEYH0DYPCFWFYH0JSIPD"
    },
    "eventType": "OUTBOUND_EVENT",
    "guid": "2K4N6J4VILWWFYH0JYA9",
    "resourcesReconciled": false,
    "status": "NEEDS_UPDATE",
    "triggers": [
        {
            "action": "WORKFLOW",
            "description": "Intended to queue up instances of Corrective Action Reports transitioning from the Corrective Action Plan Approved? step to the Corrective Action step.",
            "guid": "L3N6P2NE14FCVEXGZIIQ",
            "name": "Corrective Action Report: Plan Step Approval",
            "resource": "QUALITY"
        }
    ]
}
```
Request with an invalid GUID.

```
{  
   "status":400,
   "errors":[  
      {  
         "code":3011,
         "message":"The guid \"5N7Q9M7YL0Z6P8RATFCI\" is not valid."
      }
   ]
}
```
