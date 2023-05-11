# GET Training Plan Items


/trainingplans/&lt;GUID&gt;/items

Returns all the items associated within a specific Training Plan. In terms of the browser\-based application, this endpoint returns the items located within the Items view of a specific Training Plan.

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content\-type<br> | application/json<br> |   |

## Response Codes

| Code<br> | Description<br> |
|  --- |  --- | 
| 200<br> | Success<br> |
| 400<br> | Failure<br> |

## Response Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| Content\-Length<br> | number<br> | number of characters in response<br> |
| Content\-Type<br> | application/json<br> | content type of response<br> |
| Date<br> | date<br> | today's date and time<br> |
| Server<br> | ArenaSolutions<br> |   |
| X\-Arena\-Next\-Request\-Limit\-Reset<br> | date<br> | the scheduled time for resetting of the count<br> |
| X\-Arena\-Requests\-Remaining<br> | number<br> | how many calls left<br> |

## Sample Response Body
Get the items within the Items view  of  a Training Plan.



GET /trainingplans/&lt;GUID&gt;/items

```
{
    "count": 6,
    "results": [
        {
            "guid": "6O8RAN8ZMP6Q9SBUDTFF",
            "item": {
                "guid": "7P9SBO90NQ9H0F3XUEJR",
                "name": "SOP, Production and Process Management",
                "number": "020-00008",
                "revisionNumber": "A",
                "revisionStatus": "EFFECTIVE",
                "url": {
                    "api": "https://api.arenasolutions.com/v1/items/7P9SBO90NQ9H0F3XUEJR",
                    "app": "https://app.bom.com/7P9SBO90NQ9H0F3XUEJR"
                }
            }
        },
        {
            "guid": "7P9SBO90NQ7RATCVEUGZ",
            "item": {
                "guid": "WEYH0DYPCFY6P4SMJ3DL",
                "name": "SOP, Risk Management",
                "number": "020-00006",
                "revisionNumber": "A",
                "revisionStatus": "EFFECTIVE",
                "url": {
                    "api": "https://api.arenasolutions.com/v1/items/WEYH0DYPCFY6P4SMJ3DL",
                    "app": "https://app.bom.com/WEYH0DYPCFY6P4SMJ3DL"
                }
            }
        },
        {
            "guid": "9RBUDQB2PS9TCVEXGWHX",
            "item": {
                "guid": "1J3M5I3UHK3BU9XRO8B3",
                "name": "SOP, Control of Nonconforming Material",
                "number": "020-00010",
                "revisionNumber": "A",
                "revisionStatus": "EFFECTIVE",
                "url": {
                    "api": "https://api.arenasolutions.com/v1/items/1J3M5I3UHK3BU9XRO8B3",
                    "app": "https://app.bom.com/1J3M5I3UHK3BU9XRO8B3"
                }
            }
        },
        ...
    ]
}     
```
