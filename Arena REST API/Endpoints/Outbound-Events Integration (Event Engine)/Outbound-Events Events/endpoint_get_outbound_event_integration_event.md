# GET Outbound-Event Integration Event


/outboundevents/&lt;GUID&gt;/events/&lt;GUID&gt;

Returns a specific event for an outbound\-event integration with a specific GUID.

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
Get a specific outbound\-event integration event.



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
