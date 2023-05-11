# GET Training Plans Associated With A File


files/&lt;GUID&gt;/trainingplans

Returns all the files associated within a specific Training Plan. In terms of the browser\-based application, this endpoint returns the Training Plans located within the Associations view of a specific File.

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
