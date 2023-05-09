# GET Request Number Sequences


/settings/requests/numbersequences



/settings/requests/numbersequences/&lt;GUID&gt;

This returns  Request Number Sequences available in the workspace. Appending a GUID to the URL returns the number format with that GUID.  

Request Number Sequences consist of a list of  prefixes and an auto\-incrementing number field.

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
Get all Request number formats defined for the workspace



/settings/requests/numbersequences

```
{
    "count": 13,
    "results": [
        {
            "creationDateTime": "2008-03-07T18:40:23Z",
            "guid": "R9TCV8TK7AQN6P76AXNQ",
            "lastUsed": "000000",
            "name": "Document Change Request",
            "nextValue": "000001",
            "prefixes": [
                {
                    "guid": "8QATCPA1OR73M5NPBWL9",
                    "value": "DCR-"
                }
            ]
        },
        {
            "creationDateTime": "2008-03-04T20:04:47Z",
            "guid": "O6Q9S5QH47NK3M437UKO",
            "lastUsed": "000005",
            "name": "Engineering Change Request",
            "nextValue": "000009",
            "prefixes": [
                {
                    "guid": "ASCVERC3QT95O7PRDYND",
                    "value": "ECR-"
                }
            ]
        },
        {
            "creationDateTime": "2008-03-04T20:04:47Z",
            "guid": "N5P8R4PG36MJ2L326TJ8",
            "lastUsed": "000003",
            "name": "Manufacturing Change Request",
            "nextValue": "000004",
            "prefixes": [
                {
                    "guid": "CUEXGTE5SVB7Q9RTF0P8",
                    "value": "MCR-"
                }
            ]
        },
        ...
    ]
}
```
Get a Request number format with a specific GUID



/settings/requests/numbersequences/R9TCV8TK7AQN6P76AXNQ

```
{
    "creationDateTime": "2008-03-07T18:40:23Z",
    "guid": "R9TCV8TK7AQN6P76AXNQ",
    "lastUsed": "000000",
    "name": "Document Change Request",
    "nextValue": "000001",
    "prefixes": [
        {
            "guid": "8QATCPA1OR73M5NPBWL9",
            "value": "DCR-"
        }
    ]
}
```
