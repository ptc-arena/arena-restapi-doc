# GET Training Plans Associated With An Item
/items/&lt;GUID&gt;/trainingplans

Returns all the  Training Plans that use a specific Item. Using the browser-based application as a point of comparison, this endpoint returns the Training Plans within the Training view, Training Plans subview of a specific Item.

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
Get the Training Plan records within the Training view, Training Plans subview  of  an Item.

GET /items/&lt;GUID&gt;/trainingplans

```
{
    "count": 2,
    "results": [
        {
            "guid": "DVFYHUF6TW2M5O7Q9S01",
            "trainingplan": {
                "guid": "1J3M5I3UHK1M5O7Q9S0V",
                "number": "TRP-000002"
            }
        },
        {
            "guid": "R9TCV8TK7AG0J2L4NZBT",
            "trainingplan": {
                "guid": "FXH0JWH8VYF0J2L4NZB8",
                "number": "TRP-000004"
            }
        }
    ]
}     
```
