# GET Request Number Prefixes


/settings/requests/numbersequenceprefixes

This returns all  Request Number Prefixes available for the workspace.

Request number formats in Arena consist of a prefix \(such as ECR\) and a six\-digit autogenerating sequence \(such as 000001\), separated by a dash.

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
