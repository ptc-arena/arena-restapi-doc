# GET A Training Record Associated With An Item


/items/&lt;GUID&gt;/trainingrecords/&lt;GUID&gt;

Returns a specific Item's training record associated with a specific  Training Plans. Using the browser\-based application as a point of comparison, this endpoint returns a specific training record of a specific Item within the Records view of a specific Training Plan.

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
Get a specific training record with a given GUID associated with an Item.

GET /items/&lt;GUID&gt;/trainingrecords/&lt;GUID&gt;

```
{
    "dueDate": "2022-07-07T06:59:59Z",
    "guid": "L3N6P2NE14K2L4N6D8E2",
    "signedDateTime": "2022-04-29T06:42:37Z",
    "trainingplan": {
        "guid": "FXH0JWH8VYF0J2L4NZB8",
        "number": "TRP-000004"
    }
}
```
