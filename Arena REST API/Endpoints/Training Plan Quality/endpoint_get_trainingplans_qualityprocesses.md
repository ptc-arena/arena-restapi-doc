# GET Training Plan Quality Process References


/trainingplans/&lt;GUID&gt;/quality

Returns all the Quality Processes and the specific step associated within a specific Training Plan. Using the browser\-based application as a point of comparison, this endpoint returns the Quality Process \(and the specified step\) located within the References view of a specific Training Plan.

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
Get the Quality Processes \(and their respective steps\) within the Reference view  of  a Training Plan.



GET /trainingplans/&lt;GUID&gt;/quality

```
{
    "count": 2,
    "results": [
        {
            "guid": "P7RAT6RI58PJ2L4M1RDH",
            "quality": {
                "guid": "M4O7Q3OF25OK3M5O7KU3",
                "number": "NCMR-000001",
                "step": {
                    "guid": "N5P8R4PG36PL4N6P8LVG",
                    "name": "Nonconformance Description"
                }
            }
        },
        {
            "guid": "UCWFYBWNADUO7Q9R6WHK",
            "quality": {
                "guid": "K2M5O1MD03MI1K3MVZIC",
                "number": "CAR-000003",
                "step": {
                    "guid": "P7RAT6RI58RN6P8R04NA",
                    "name": "Corrective Action"
                }
            }
        }
    ]
}
```
