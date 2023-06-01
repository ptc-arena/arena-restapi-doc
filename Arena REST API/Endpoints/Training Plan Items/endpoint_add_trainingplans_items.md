# POST Add Training Plan Item
/trainingplans/&lt;GUID&gt;/items

This endpoint adds an Item to a Training Plan. In order to add a user to  a Training Plan, the user account executing the endpoint must be the Training Plan Manager.  Using the browser-based application as a point of comparison, this endpoint adds a specific item to the Items view of a specific Training Plan.

## Request Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content-type<br> | application/json<br> |   |

## Response Codes

| Code<br> | Description<br> |
|  --- |  --- | 
| 201<br> | Success<br> |
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

## Sample Requests and Responses
Add an item to  a Training Plan.

POST /trainingplans/&lt;GUID&gt;/items

**Request** 

```
{
    "item": {
        "guid": "L3N6P2NE14NVETHB8TF2"
    }
}
```
**Response** 

```
{
    "guid": "K2M5O1MD03K4N6P8Q09D",
    "item": {
        "guid": "L3N6P2NE14NVETHB8TF2",
        "name": "SOP, Building Evacuation and Safety",
        "number": "020-00004",
        "revisionNumber": "A",
        "revisionStatus": "EFFECTIVE",
        "url": {
            "api": "https://api.arenasolutions.com/v1/items/L3N6P2NE14NVETHB8TF2",
            "app": "https://app.bom.com/L3N6P2NE14NVETHB8TF2"
        }
    }
}
```
