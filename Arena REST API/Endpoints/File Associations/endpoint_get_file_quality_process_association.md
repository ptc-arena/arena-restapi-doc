# GET File Quality Process Association
/files/&lt;GUID&gt;/qualityprocesses/&lt;GUID&gt;

Returns a  specific file's quality process association GUID  for a file with a given GUID. 

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
| Content-Length  | number  | number of characters in response  |
| Content-Type  | application/json  | content type of response  |
| Date  | date  | today's date and time  |
| Server  | ArenaSolutions  |   |
| X-Arena-Next-Request-Limit-Reset   | date  | the scheduled time for resetting of the count  |
| X-Arena-Requests-Remaining   | number  | how many calls left  |

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
