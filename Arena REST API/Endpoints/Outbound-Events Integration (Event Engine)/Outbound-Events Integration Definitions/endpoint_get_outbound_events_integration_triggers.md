# GET Outbound-Event Integration Triggers


/outboundevents/&lt;GUID&gt;/triggers

Returns all the triggers for a specific outbound event integration.

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content\-type<br> | application/json<br> |   |

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

## Sample Response Body
Get all  triggers associated with a specific outbound event integration.



GET /outboundevents/&lt;GUID&gt;/triggers

```
{
    "count": 3,
    "results": [
        {
            "action": "WORKFLOW",
            "description": "Queues up all Items that move into the Design Verification Lifeycle phase.",
            "guid": "R9TCV8TK7ALI1K3M5OQM",
            "name": "Design Verification",
            "resource": "ITEM"
        },
        {
            "action": "WORKFLOW",
            "description": "Intended to queue up instances of Corrective Action Reports transitioning from the Corrective Action Plan Approved? step to the Corrective Action step.",
            "guid": "L3N6P2NE14FCVEXGZIIQ",
            "name": "Corrective Action Report: Plan Step Approval",
            "resource": "QUALITY"
        },
        {
            "action": "WORKFLOW",
            "description": "Queues all Changes with a category of Manufacturing Change Order that move from lifecycle status of Submitted or Approved to Effective.",
            "guid": "M4O7Q3OF25GDWFYH0JPT",
            "name": "Manufacturing Change Order Release",
            "resource": "CHANGE"
        }
    ]
}
```
