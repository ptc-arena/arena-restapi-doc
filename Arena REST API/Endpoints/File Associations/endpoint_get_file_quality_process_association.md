# GET File Quality Process Association


/files/&lt;GUID&gt;/qualityprocesses/&lt;GUID&gt;

Returns a  specific file's quality process association GUID  for a file with a given GUID. 

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
A specific File Quality Process association



GET &lt;url&gt;/files/&lt;GUID&gt;/qualityprocesses/&lt;GUID&gt;

```
{  
    "guid":"9RBUZPQQZ6N3M5O79TKC",
    "qualityProcess":{  
       "guid":"4M6PUKLLU1KGZI1KYBRS",
       "number":"NCMR-000002",
       "step":{  
               "guid":"6O8RWMNNW3MI1K3M0DT2",
               "name":"Action Taken"
       }
    }
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
