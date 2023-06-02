# GET A Training Plan Associated With A File
files/&lt;GUID&gt;/trainingplans/&lt;GUID&gt;

Returns a specific Training Plan associated within a specific File. Using the browser-based application as a point of comparison, this endpoint returns a specific Training Plan located within the Associations  view of a specific File.

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
