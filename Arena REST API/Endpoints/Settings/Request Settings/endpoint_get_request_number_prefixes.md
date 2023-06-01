# GET Request Number Prefixes
/settings/requests/numbersequenceprefixes

This returns all  Request Number Prefixes available for the workspace.

Request number formats in Arena consist of a prefix \(such as ECR\) and a six-digit autogenerating sequence \(such as 000001\), separated by a dash.

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
Get all requests number prefixes

GET /settings/requests/numbersequenceprefixes

```
{
    "count": 13,
    "results": [
        {
            "guid": "8QATCPA1OR73M5NPBWL9",
            "value": "DCR-"
        },
        {
            "guid": "ASCVERC3QT95O7PRDYND",
            "value": "ECR-"
        },
        {
            "guid": "CUEXGTE5SVB7Q9RTF0P8",
            "value": "MCR-"
        },
        ...
    ]
}
```
