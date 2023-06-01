# GET File Item Associations
/files/&lt;GUID&gt;/items

Returns a list of Item association GUIDs \(and information about the associated Items\) for a File with a given GUID. 

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
Get a collection of item associations for a specific file.

GET /files/&lt;GUID&gt;/items

```
{  
   "count":2,
   "results":[  
      {  
         "guid":"7P9SXNOOX4NRATE1TMVN",
         "items":[  
            {  
               "guid":"1J3MRHIIRYHRAT5D1U08",
               "number":"100-91",
               "revisionNumber":"A",
               "status":2
            },
            {  
               "guid":"J1L49Z009GY1K3M5OHYM",
               "number":"100-91",
               "revisionNumber":"B",
               "status":1
            },
            {  
               "guid":"FXH05VWW5CV4N6MNGHDF",
               "number":"100-91",
               "revisionNumber":"C",
               "status":0
            }
         ]
      },
      {  
         "guid":"HZJ2LT22ZGZBUDWCJBAM",
         "items":[  
            {  
               "guid":"L3N6PX663K3K3HOBORT3",
               "number":"110-0001",
               "revisionNumber":"1",
               "status":2
            }
         ]
      }
   ]
}
```
Request with bad GUID

```
{  
   "status":400,
   "errors":[  
      {  
         "code":3011,
         "message":"The guid \"M4O7QY5R7FY8RATAYXNX\" is not valid."
      }
   ]
}
```
