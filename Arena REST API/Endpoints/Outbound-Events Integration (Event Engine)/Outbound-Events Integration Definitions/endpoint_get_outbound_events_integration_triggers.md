# GET Outbound-Event Integration Triggers


/outboundevents/&lt;GUID&gt;/triggers

Returns all the triggers for a specific outbound event integration.

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
