# POST Add Training Plan Quality Process


/trainingplans/&lt;GUID&gt;/quality

This endpoint adds a Quality Process \(with a specified step\) as a reference to a Training Plan.  Using the browser\-based application as a point of comparison, this endpoint adds a specific Quality Process to the Reference view of a specific Training Plan.

## Request Header

| Name | Value | Description |
|  --- |  --- |  --- | 
| arena_session_id |   | unique ID for session obtained from login |
| content\-type | application/json |   |

## Response Codes

| Code | Description |
|  --- |  --- | 
| 201 | Success |
| 400 | Failure |

## Response Header

| Name | Value | Description |
|  --- |  --- |  --- | 
| Content\-Length | number | number of characters in response |
| Content\-Type | application/json | content type of response |
| Date | date | today's date and time |
| Server | ArenaSolutions |   |
| X\-Arena\-Next\-Request\-Limit\-Reset  | date | the scheduled time for resetting of the count |
| X\-Arena\-Requests\-Remaining  | number | how many calls left |

## Sample Requests and Responses
Add a Quality Process \(with a specified step\) to  a Training Plan.



POST /trainingplans/&lt;GUID&gt;/quality



```
{
    "quality": {
        "guid": "M4O7Q3OF25OK3M5O7KU3",
        "step": {
            "guid": "N5P8R4PG36PL4N6P8LVG"
        }
    }
}
```


```
{
    "guid": "WEYH0DYPCFWQ9SBT8YJG",
    "quality": {
        "guid": "M4O7Q3OF25OK3M5O7KU3",
        "number": "NCMR-000001",
        "step": {
            "guid": "N5P8R4PG36PL4N6P8LVG",
            "name": "Nonconformance Description"
        }
    }
}
```
