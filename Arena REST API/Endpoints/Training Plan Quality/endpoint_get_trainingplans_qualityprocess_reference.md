# GET Training Plan Quality Process Reference
/trainingplans/&lt;GUID&gt;/quality/&lt;GUID&gt;

Returns a specific Quality Process associated within a specific Training Plan. Using the browser-based application as a point of comparison, this endpoint returns a specific Quality Process located within the Reference view of a specific Training Plan.

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
| Content-Length<br> | number<br> | number of characters in response<br> |
| Content-Type<br> | application/json<br> | content type of response<br> |
| Date<br> | date<br> | today's date and time<br> |
| Server<br> | ArenaSolutions<br> |   |
| X-Arena-Next-Request-Limit-Reset<br> | date<br> | the scheduled time for resetting of the count<br> |
| X-Arena-Requests-Remaining<br> | number<br> | how many calls left<br> |

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
