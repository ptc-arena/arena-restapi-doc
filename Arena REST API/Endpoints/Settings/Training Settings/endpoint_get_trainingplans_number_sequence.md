# GET Training Plan Number Sequence
/settings/trainingplans/numbersequences/&lt;GUID&gt;

Appending a GUID to the URL returns the number format with that GUID. Training Plan Number Sequence endpoint consist of a prefix and an auto-incrementing number field.

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
