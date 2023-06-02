# GET Training Records Associated With An Item
/items/&lt;GUID&gt;/trainingrecords

Returns a specific Item's training records across all the  Training Plans it is associated with. Using the browser-based application as a point of comparison, this endpoint returns the training records of a specific Item within the Records view of all Training Plans associated with that Item.

## Request Header

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| arena_session_id  |   | unique ID for session obtained from login  |
| content-type  | application/json  |   |

## Parameters

| Name  | Value  | Description  |
|  --- |  --- |  --- | 
| offset  | integer  | Specifies the position in the list of all changes where results should begin. All changes before the offset in the search results are ignored. The default value is 0.  |
| limit  | integer  | Specifies the number of results that should be returned. By default the maximum number of objects is 20. Can return up 400.  |

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
Get the training records of  an Item.

GET /items/&lt;GUID&gt;/trainingrecords

```
{
    "count": 2,
    "results": [
        {
            "guid": "DVFYHUF6TW2M5O7Q9S01",
            "trainingplan": {
                "guid": "1J3M5I3UHK1M5O7Q9S0V",
                "number": "TRP-000002"
            }
        },
        {
            "guid": "R9TCV8TK7AG0J2L4NZBT",
            "trainingplan": {
                "guid": "FXH0JWH8VYF0J2L4NZB8",
                "number": "TRP-000004"
            }
        }
    ]
}     
```
