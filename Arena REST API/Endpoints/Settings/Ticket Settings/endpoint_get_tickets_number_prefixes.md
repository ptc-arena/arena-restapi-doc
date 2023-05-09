# GET Tickets Number Sequence Prefixes


/settings/tickets/numbersequenceprefixes

This returns all  Tickets Number Sequences Prefixes available for the workspace.

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
| Content\-Length | number | number of characters in the response |
| Content\-Type | application/json | content type of response |
| Date | date | today's date and time |
| Server | ArenaSolutions |   |
| X\-Arena\-Next\-Request\-Limit\-Reset  | date | the scheduled time for resetting of the count |
| X\-Arena\-Requests\-Remaining  | number | how many calls left |

## Sample Response Body
Get all tickets number prefixes





GET /settings/tickets/numbersequenceprefixes

```
{
    "count": 2,
    "results": [
        {
            "guid": "M4O7Q3OF25LH0J2L4NWL",
            "value": "DEF-"
        },
        {
            "guid": "L3N6P2NE14KGZI1K3MVY",
            "value": "REQ-"
        }
    ]
}
```
