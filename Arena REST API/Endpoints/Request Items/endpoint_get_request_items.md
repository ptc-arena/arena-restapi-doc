# GET Request Items


/requests/&lt;GUID&gt;/items

Returns all Request Items  included in a request with a given GUID. 

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
| Content\-Type<br> | application/json<br> | content type of response<br> |
| Date<br> | date<br> | today's date and time<br> |
| Server<br> | ArenaSolutions<br> |   |
| X\-Arena\-Next\-Request\-Limit\-Reset<br> | date<br> | the scheduled time for resetting of the count<br> |
| X\-Arena\-Requests\-Remaining<br> | number<br> | how many calls left<br> |

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
