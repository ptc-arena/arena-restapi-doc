# GET File Request Associations


/files/&lt;GUID&gt;/requests

Returns a list of Requests association GUIDs \(and limited information about the associated Requests\) for a File with a given GUID. 

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
| Content\-Length<br> | number<br> | number of characters in response<br> |
| Content\-Type<br> | application/json<br> | content type of response<br> |
| Date<br> | date<br> | today's date and time<br> |
| Server<br> | ArenaSolutions<br> |   |
| X\-Arena\-Next\-Request\-Limit\-Reset<br> | date<br> | the scheduled time for resetting of the count<br> |
| X\-Arena\-Requests\-Remaining<br> | number<br> | how many calls left<br> |

## Sample Response Body
Requests  associations for a specific file

 

GET &lt;url&gt;/files/&lt;GUID&gt;/requests

```
{  
   "count":6,
   "results":[  
      {  
         "guid":"4S1JM4YCFHIWJ45QNWJ0",
         "request":{  
            "guid":"Z2M6BZX2ZJAYI06T6RCG",
            "number":"ECR-000004"
         }
      },
      {  
         "guid":"RTZ2LYJAX0JTCVAHHI66",
         "request":{  
            "guid":"N5P8R4PG36PO7QXI618R",
            "number":"ECR-000014"
         }
      },
      {  
         "guid":"9Z6P8L6XKN4L4N6P7X7E",
         "request":{  
            "guid":"O6Q9S5QH47QP8RYJ729F",
            "number":"ECR-000033"
         }
      },
      ...
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
