# GET A Training Plan Associated With A File
files/&lt;GUID&gt;/trainingplans/&lt;GUID&gt;

Returns a specific Training Plan associated within a specific File. Using the browser-based application as a point of comparison, this endpoint returns a specific Training Plan located within the Associations  view of a specific File.

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
Get a specific Training Plan with a given GUID within the Associations view of a  File with a given GUID.

GET files/&lt;GUID&gt;/trainingplans/&lt;GUID&gt;

```
{
    "guid": "4M6P8L6XKN0FYH0IXN99",
    "trainingplan": {
        "guid": "FXH0JWH8VYF0J2L4NZB8",
        "number": "TRP-000004"
    }
}
```
