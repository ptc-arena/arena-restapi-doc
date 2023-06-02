# GET Training Plan Number Sequence
/settings/trainingplans/numbersequences/&lt;GUID&gt;

Appending a GUID to the URL returns the number format with that GUID. Training Plan Number Sequence endpoint consist of a prefix and an auto-incrementing number field.

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
Get a specific Training number sequences with a specific GUID

/settings/trainingplans/numbersequences/2K4N6J4VIL1YH0J2L3CX

```
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
```
