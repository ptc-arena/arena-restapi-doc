# GET Training Plan Record
/trainingplans/&lt;GUID&gt;/records/&lt;GUID&gt;

Returns a specific training record associated within a specific Training Plan. Using the browser-based application as a point of comparison, this endpoint returns a specific record located within the Records view of a specific Training Plan.

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
