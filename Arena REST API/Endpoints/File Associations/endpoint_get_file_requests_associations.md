# GET File Request Associations


/files/&lt;GUID&gt;/requests

Returns a list of Requests association GUIDs \(and limited information about the associated Requests\) for a File with a given GUID. 

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
