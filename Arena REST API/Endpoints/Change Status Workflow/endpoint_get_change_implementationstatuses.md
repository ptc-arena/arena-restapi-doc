# GET Change Implementation Statuses
settings/changes/implementationstatuses

The GET Change Implementation Statuses endpoint returns all the implementation statuses for a Change in a workspaace. Change Administrators use the implementation statuses to set the implementation status when moving a Change from the EFFECTIVE to the COMPLETED lifecycle status or when moving a Change from the COMPLETED to the EFFECTIVE lifecycle status. Implementation statuses can also be used when moving a Change from the EXPIRED to the COMPLETED lifecycle status. For examples using the implementationStatus property, see POST Change Status \(Completed\) or POST Change Status \(Unmark as Complete\).

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
