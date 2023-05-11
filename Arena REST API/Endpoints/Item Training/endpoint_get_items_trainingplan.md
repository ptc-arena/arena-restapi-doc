# GET A Training Plan Associated With An Item


/items/&lt;GUID&gt;/trainingplans/&lt;GUID&gt;

Returns a specific Training Plan associated within a specific Item. Using the browser\-based application as a point of comparison, this endpoint returns a specific Training Plan located within the Training view, Training Plans subview of a specific Item.

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
Get a specific Training Plan with a given GUID within the Training view,  Training Plans subview of an Item.

GET /items/&lt;GUID&gt;/trainingplans/&lt;GUID&gt;

```
{
    "guid": "DVFYHUF6TW2M5O7Q9S01",
    "trainingplan": {
        "guid": "1J3M5I3UHK1M5O7Q9S0V",
        "number": "TRP-000002"
    }
}
```
