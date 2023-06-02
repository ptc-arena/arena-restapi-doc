# GET Training Plans Associated With A File
files/&lt;GUID&gt;/trainingplans

Returns all the files associated within a specific Training Plan. In terms of the browser-based application, this endpoint returns the Training Plans located within the Associations view of a specific File.

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
Get the Training Plans within the Associations view  of  a File.

GET files/&lt;GUID&gt;/trainingplans

```
{
    "count": 2,
    "results": [
        {
            "guid": "HZJ2LYJAX0DSBUDVA6PX",
            "trainingplan": {
                "guid": "1J3M5I3UHK1M5O7Q9S0V",
                "number": "TRP-000002"
            }
        },
        {
            "guid": "4M6P8L6XKN0FYH0IXN99",
            "trainingplan": {
                "guid": "FXH0JWH8VYF0J2L4NZB8",
                "number": "TRP-000004"
            }
        }
    ]
}        
```
