# GET Request Affected Item
/requests/&lt;GUID&gt;/items/&lt;GUID&gt;

Returns a Request  Item  with a given GUID included in a request with a given GUID.

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
| Content-Type  | application/json  | content type of response  |
| Date  | date  | today's date and time  |
| Server  | ArenaSolutions  |   |
| X-Arena-Next-Request-Limit-Reset   | date  | the scheduled time for resetting of the count  |
| X-Arena-Requests-Remaining   | number  | how many calls left  |

## Sample Response Body
Get a specific  item included in a request

GET /requests/&lt;GUID&gt;/items/&lt;GUID&gt;

```
{
    "guid": "TBVEXAVM9CPO7QZFFDRY",
    "item": {
        "guid": "3L5O7K5WJM5DWEO7JBIR",
        "name": "Screw, M3 x 6, ST, Torx",
        "number": "472-00001",
        "revisionNumber": "A",
        "revisionStatus": "EFFECTIVE",
        "url": {
            "api": "https://api.arenasolutions.com/v1/items/3L5O7K5WJM5DWEO7JBIR",
            "app": "https://app.bom.com/3L5O7K5WJM5DWEO7JBIR"
        }
    },
    "notes": "Similar to 472-00002 but with Torx drive style"
}
```
Request with invalid GUID

```
{  
   "status":400,
   "errors":[  
      {  
         "code":3011,
         "message":"The guid \"XFWQ0GZGZDJ015J12\" is not valid."
      }
   ]
}
```
