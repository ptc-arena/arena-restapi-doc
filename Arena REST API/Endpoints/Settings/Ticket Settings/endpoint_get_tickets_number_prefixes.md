# GET Tickets Number Sequence Prefixes
/settings/tickets/numbersequenceprefixes

This returns all  Tickets Number Sequences Prefixes available for the workspace.

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
| Content-Length<br> | number<br> | number of characters in the response<br> |
| Content-Type<br> | application/json<br> | content type of response<br> |
| Date<br> | date<br> | today's date and time<br> |
| Server<br> | ArenaSolutions<br> |   |
| X-Arena-Next-Request-Limit-Reset<br> | date<br> | the scheduled time for resetting of the count<br> |
| X-Arena-Requests-Remaining<br> | number<br> | how many calls left<br> |

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
