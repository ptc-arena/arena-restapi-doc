# GET Training Plan Number Sequences
/settings/trainingplans/numbersequences

This first url returns all  Training Plan number sequences available in the workspace. .  

Training Number Sequences consist of a list of  prefixes and an auto-incrementing number field.

## Request Header

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| arena_session_id  |   | unique ID for session obtained from login  |
| content-type  | application/json  |   |

## Response Codes

| Code  | Description  |
|  --- |  --- | 
| 200  | Success  |
| 400  | Failure  |

## Response Header

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| Content-Length  | number  | number of characters in the response  |
| Content-Type  | application/json  | content type of response  |
| Date  | date  | today's date and time  |
| Server  | ArenaSolutions  |   |
| X-Arena-Next-Request-Limit-Reset   | date  | the scheduled time for resetting of the count  |
| X-Arena-Requests-Remaining   | number  | how many calls left  |

## Sample Response Body
Get all Training number sequences defined for the workspace

/settings/trainingplans/numbersequences

```
{
    "count": 2,
    "results": [
        {
            "creationDateTime": "2022-04-19T06:22:03Z",
            "guid": "R9TCV8TK7AQN6P8RAID3",
            "lastUsed": "000000",
            "name": "Standard Operating Procedures",
            "nextValue": "000001",
            "prefixes": [
                {
                    "guid": "0I2L4H2TGJZVEXGZIQI8",
                    "value": "SOP"
                }
            ]
        },
        {
            "creationDateTime": "2016-06-26T15:20:47Z",
            "guid": "2K4N6J4VIL1YH0J2L3CX",
            "lastUsed": "000003",
            "name": "TRP",
            "nextValue": "000004",
            "prefixes": [
                {
                    "guid": "3L5O7K5WJM2YH0J2L3C7",
                    "value": "TRP-"
                }
            ]
        }
    ]
}
```
