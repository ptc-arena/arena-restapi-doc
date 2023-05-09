# GET Training Plan Item


/trainingplans/&lt;GUID&gt;/items/&lt;GUID&gt;

Returns a specific item associated within a specific Training Plan. In terms of the browser\-based application, this endpoint returns  a specific item located within the Files view of a specific Training Plan.

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
