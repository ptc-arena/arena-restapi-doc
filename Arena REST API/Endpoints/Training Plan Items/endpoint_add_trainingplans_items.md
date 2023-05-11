# POST Add Training Plan Item


/trainingplans/&lt;GUID&gt;/items

This endpoint adds an Item to a Training Plan. In order to add a user to  a Training Plan, the user account executing the endpoint must be the Training Plan Manager.  Using the browser\-based application as a point of comparison, this endpoint adds a specific item to the Items view of a specific Training Plan.

## Request Header

| Name | Value | Description |
|  --- |  --- |  --- | 
| arena_session_id |   | unique ID for session obtained from login |
| content\-type | application/json |   |

## Response Codes

| Code | Description |
|  --- |  --- | 
| 201 | Success |
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

## Sample Requests and Responses
Add an item to  a Training Plan.



POST /trainingplans/&lt;GUID&gt;/items



```
{
    "item": {
        "guid": "L3N6P2NE14NVETHB8TF2"
    }
}
```


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
