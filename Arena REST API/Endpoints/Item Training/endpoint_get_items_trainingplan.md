# GET A Training Plan Associated With An Item


/items/&lt;GUID&gt;/trainingplans/&lt;GUID&gt;

Returns a specific Training Plan associated within a specific Item. Using the browser\-based application as a point of comparison, this endpoint returns a specific Training Plan located within the Training view, Training Plans subview of a specific Item.

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
