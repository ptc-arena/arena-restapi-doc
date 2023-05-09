# GET Change Implementation Statuses


settings/changes/implementationstatuses

The GET Change Implementation Statuses endpoint returns all the implementation statuses for a Change in a workspaace. Change Administrators use the implementation statuses to set the implementation status when moving a Change from the EFFECTIVE to the COMPLETED lifecycle status or when moving a Change from the COMPLETED to the EFFECTIVE lifecycle status. Implementation statuses can also be used when moving a Change from the EXPIRED to the COMPLETED lifecycle status. For examples using the implementationStatus property, see POST Change Status \(Completed\) or POST Change Status \(Unmark as Complete\).

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
Get the Implementation Statuses for Changes in a workspace.



GET /settings/changes/implementationstatuses

```
{
    "count": 5,
    "results": [
        {
            "guid": "EWGZIVG7UXATCVEXGZIT",
            "name": "NOT_STARTED"
        },
        {
            "guid": "FXH0JWH8VYBUDWFYH0JM",
            "name": "IN_PROGRESS"
        },
        {
            "guid": "GYI1KXI9WZCVEXGZI1KC",
            "name": "NEEDS_ATTN"
        },
        {
            "guid": "HZJ2LYJAX0DWFYH0J2LC",
            "name": "DONE"
        },
        {
            "guid": "I0K3MZKBY1EXGZI1K3M9",
            "name": "BLANK"
        }
    ]
}
```
