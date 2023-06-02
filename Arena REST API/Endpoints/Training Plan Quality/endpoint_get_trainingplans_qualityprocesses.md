# GET Training Plan Quality Process References
/trainingplans/&lt;GUID&gt;/quality

Returns all the Quality Processes and the specific step associated within a specific Training Plan. Using the browser-based application as a point of comparison, this endpoint returns the Quality Process \(and the specified step\) located within the References view of a specific Training Plan.

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
| Content-Length  | number  | number of characters in response  |
| Content-Type  | application/json  | content type of response  |
| Date  | date  | today's date and time  |
| Server  | ArenaSolutions  |   |
| X-Arena-Next-Request-Limit-Reset   | date  | the scheduled time for resetting of the count  |
| X-Arena-Requests-Remaining   | number  | how many calls left  |

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
