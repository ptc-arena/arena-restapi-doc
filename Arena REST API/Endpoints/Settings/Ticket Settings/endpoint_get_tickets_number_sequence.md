# GET Tickets Number Sequences
/settings/tickets/numbersequences

/settings/tickets/numbersequences/&lt;GUID&gt;

This returns  Tickets Number Sequences available in the workspace. Appending a GUID to the URL returns the number format with that GUID.  

Tickets Number Sequences consist of a list of  prefixes and an auto-incrementing number field.

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
Get all Tickets number sequences defined for the workspace

/settings/tickets/numbersequences

```
{
    "count": 2,
    "results": [
        {
            "creationDateTime": "2016-12-13T19:24:21Z",
            "guid": "3L5O7K5WJM2ZI1K3M5F5",
            "lastUsed": "000002",
            "name": "Defects",
            "nextValue": "000003",
            "prefixes": [
                {
                    "guid": "M4O7Q3OF25LH0J2L4NWL",
                    "value": "DEF-"
                }
            ]
        },
        {
            "creationDateTime": "2016-12-13T19:24:21Z",
            "guid": "2K4N6J4VIL1YH0J2L4EI",
            "lastUsed": "000005",
            "name": "Requirements",
            "nextValue": "000006",
            "prefixes": [
                {
                    "guid": "L3N6P2NE14KGZI1K3MVY",
                    "value": "REQ-"
                }
            ]
        }
    ]
}
```
Get a Tickets number sequences with a specific GUID

/settings/tickets/numbersequences/&lt;GUID&gt;

```
{
    "creationDateTime": "2016-12-13T19:24:21Z",
    "guid": "3L5O7K5WJM2ZI1K3M5F5",
    "lastUsed": "000002",
    "name": "Defects",
    "nextValue": "000003",
    "prefixes": [
        {
            "guid": "M4O7Q3OF25LH0J2L4NWL",
            "value": "DEF-"
        }
    ]
}
```
