# GET Tickets Number Sequences


/settings/tickets/numbersequences



/settings/tickets/numbersequences/&lt;GUID&gt;

This returns  Tickets Number Sequences available in the workspace. Appending a GUID to the URL returns the number format with that GUID.  

Tickets Number Sequences consist of a list of  prefixes and an auto\-incrementing number field.

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
