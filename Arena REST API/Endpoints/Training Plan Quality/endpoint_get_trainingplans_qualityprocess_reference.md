# GET Training Plan Quality Process Reference


/trainingplans/&lt;GUID&gt;/quality/&lt;GUID&gt;

Returns a specific Quality Process associated within a specific Training Plan. Using the browser\-based application as a point of comparison, this endpoint returns a specific Quality Process located within the Reference view of a specific Training Plan.

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
| Content\-Length | number | number of characters in response |
| Content\-Type | application/json | content type of response |
| Date | date | today's date and time |
| Server | ArenaSolutions |   |
| X\-Arena\-Next\-Request\-Limit\-Reset  | date | the scheduled time for resetting of the count |
| X\-Arena\-Requests\-Remaining  | number | how many calls left |

## Sample Response Body
Get a specific Quality Process with a given GUID within the Reference view of a  Training Plan with a given GUID.

GET /trainingplans/&lt;GUID&gt;/quality/&lt;GUID&gt;

```
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
}
```
