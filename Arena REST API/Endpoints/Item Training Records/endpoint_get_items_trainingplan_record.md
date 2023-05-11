# GET A Training Record Associated With An Item


/items/&lt;GUID&gt;/trainingrecords/&lt;GUID&gt;

Returns a specific Item's training record associated with a specific  Training Plans. Using the browser\-based application as a point of comparison, this endpoint returns a specific training record of a specific Item within the Records view of a specific Training Plan.

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
