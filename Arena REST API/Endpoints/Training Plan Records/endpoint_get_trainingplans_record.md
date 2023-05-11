# GET Training Plan Record


/trainingplans/&lt;GUID&gt;/records/&lt;GUID&gt;

Returns a specific training record associated within a specific Training Plan. Using the browser\-based application as a point of comparison, this endpoint returns a specific record located within the Records view of a specific Training Plan.

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
Get a specific training record with a given GUID within the Records view of a  Training Plan with a given GUID.

GET /trainingplans/&lt;GUID&gt;/records/&lt;GUID&gt;

```
{
    "dueDate": "2016-09-18T06:59:59Z",
    "guid": "N5P8R4PG36M4N6P8Q0RJ",
    "item": {
        "guid": "7P9SBO90NQ9H0F3XUEJR",
        "name": "SOP, Production and Process Management",
        "number": "020-00008",
        "revisionNumber": "A",
        "revisionStatus": "EFFECTIVE",
        "url": {
            "api": "https://api.arenasolutions.com/v1/items/7P9SBO90NQ9H0F3XUEJR",
            "app": "https://app.bom.com/7P9SBO90NQ9H0F3XUEJR"
        }
    },
    "signedDateTime": "2017-03-17T22:56:08Z",
    "user": {
        "email": "hwalker@everyroadgps.com",
        "fullName": "Heidi Walker",
        "guid": "WEYH0DYPCFWFYH0JSIPD"
    }
}
```
