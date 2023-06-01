# GET Training Plan Item
/trainingplans/&lt;GUID&gt;/items/&lt;GUID&gt;

Returns a specific item associated within a specific Training Plan. In terms of the browser-based application, this endpoint returns  a specific item located within the Files view of a specific Training Plan.

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
Get a specific item with a given GUID within the Items view of a  Training Plan with a given GUID.

GET /trainingplans/&lt;GUID&gt;/items/&lt;GUID&gt;

```
{
    "guid": "CUEXGTE5SVCWFYH0JZKJ",
    "item": {
        "guid": "R9TCV8TK7AT1KZNHEY9O",
        "name": "SOP, Inspection and Test",
        "number": "020-00005",
        "revisionNumber": "A",
        "revisionStatus": "EFFECTIVE",
        "url": {
            "api": "https://api.arenasolutions.com/v1/items/R9TCV8TK7AT1KZNHEY9O",
            "app": "https://app.bom.com/R9TCV8TK7AT1KZNHEY9O"
        }
    }
}   
```
