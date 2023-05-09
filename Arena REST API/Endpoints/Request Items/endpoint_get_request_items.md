# GET Request Items


/requests/&lt;GUID&gt;/items

Returns all Request Items  included in a request with a given GUID. 

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
| Content\-Type | application/json | content type of response |
| Date | date | today's date and time |
| Server | ArenaSolutions |   |
| X\-Arena\-Next\-Request\-Limit\-Reset  | date | the scheduled time for resetting of the count |
| X\-Arena\-Requests\-Remaining  | number | how many calls left |

## Sample Response Body
Get all items included in a request



GET /requests/&lt;GUID&gt;/items

```
{
    "count": 3,
    "results": [
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
        },
        {
            "guid": "UCWFYBWNADQP8R0GGESV",
            "item": {
                "guid": "7P9SBO90NQ9H0IRHBGKB",
                "name": "Screw, M3 x 6, ST, PH",
                "number": "472-00002",
                "revisionNumber": "A",
                "revisionStatus": "EFFECTIVE",
                "url": {
                    "api": "https://api.arenasolutions.com/v1/items/UCWFYBWNADQP8R0GGESV",
                    "app": "https://app.bom.com/UCWFYBWNADQP8R0GGESV"
                }
            },
            "notes": "Self-tapping Pan head screw with Phillips drive style"
        },
        {
            "guid": "VDXGZCXOBERQ9S1HHFT8",
            "item": {
                "guid": "HZJ2LYJAX0JRAS1RLQU7",
                "name": "Screw, M2 x 5, ST, PH",
                "number": "472-00003",
                "revisionNumber": "A",
                "revisionStatus": "EFFECTIVE",
                "url": {
                    "api": "https://api.arenasolutions.com/v1/items/HZJ2LYJAX0JRAS1RLQU7",
                    "app": "https://app.bom.com/HZJ2LYJAX0JRAS1RLQU7"
                }
            },
            "notes": "Self-tapping Pan head screw with Phillips drive style"
        },   
    ]
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
