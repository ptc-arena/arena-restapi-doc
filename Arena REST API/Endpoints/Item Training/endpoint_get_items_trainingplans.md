# GET Training Plans Associated With An Item


/items/&lt;GUID&gt;/trainingplans

Returns all the  Training Plans that use a specific Item. Using the browser\-based application as a point of comparison, this endpoint returns the Training Plans within the Training view, Training Plans subview of a specific Item.

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
